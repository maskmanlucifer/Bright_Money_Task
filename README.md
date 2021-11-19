### Bright_Money_Task
### Local Enviornment Setup
    1. Create and Enter virtual enviorment
          virtualenv brightTask
          source brightTask/bin/activate
          
    2. Install all dependencies
          pip3 install -r requirements.txt
          
    3. Setup Models
          python3 manage.py makemigrations
          python3 manage.py migrate 
       
    4. Run server
          python3 manage.py runserver
          
    5. Start celery worker
          celery -A Plaid_Manager_API worker -l info
