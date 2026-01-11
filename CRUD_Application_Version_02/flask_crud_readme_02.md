import os
from flask import Flask, render_template, request, redirect, url_for
from models import db, User

# -------------------------------------------------------------------
# Absolute base directory
# -------------------------------------------------------------------
BASE_DIR = os.path.dirname(os.path.abspath(__file__))

app = Flask(
    __name__,
    template_folder=os.path.join(BASE_DIR, "templates"),
    static_folder=os.path.join(BASE_DIR, "static")
)

# -------------------------------------------------------------------
# Database configuration
# -------------------------------------------------------------------
app.config['SQLALCHEMY_DATABASE_URI'] = f"sqlite:///{os.path.join(BASE_DIR, 'users.db')}"
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False

db.init_app(app)

# -------------------------------------------------------------------
# Create tables
# -------------------------------------------------------------------
with app.app_context():
    db.create_all()

# -------------------------------------------------------------------
# Routes
# -------------------------------------------------------------------
@app.route('/')
def index():
    users = User.query.all()
    return render_template('index.html', users=users)

@app.route('/add', methods=['GET', 'POST'])
def add_user():
    if request.method == 'POST':
        name = request.form['name']
        db.session.add(User(name=name))
        db.session.commit()
        return redirect(url_for('index'))
    return render_template('add.html')

@app.route('/edit/<int:id>', methods=['GET', 'POST'])
def edit_user(id):
    user = User.query.get_or_404(id)
    if request.method == 'POST':
        user.name = request.form['name']
        db.session.commit()
        return redirect(url_for('index'))
    return render_template('edit.html', user=user)

@app.route('/delete/<int:id>', endpoint='delete_user')
def delete_user(id):
    user = User.query.get_or_404(id)
    db.session.delete(user)
    db.session.commit()
    return redirect(url_for('index'))

# -------------------------------------------------------------------
# App start
# -------------------------------------------------------------------
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)