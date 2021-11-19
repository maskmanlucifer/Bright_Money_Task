### :dart: Bright_Money_Task
### :computer: Local Enviornment Setup
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
          
### :hammer_and_wrench:Models
### AccountModel
    account_id
    bank_item
    balance_available
    balance_current
    
### APILogModel
    request_id
    api_type
    date_log
    
### TransactionModel
    transaction_id
    account
    amount
    date
    name 
    pending

### BankItemModel
    bank_item_id
    access_token
    request_id
    user
    
### :anchor: API Endpoints (Port : 8000)
### Users API
    /users/register/                      => For registering user
    /users/login/                         => For logging in user
    /users/logout/                        => For logging out user
    
### Token Exchange API (Get Method)
    /token_exchange/home/                 =>  For getting public token   
    /token_exchange/get_items/            =>  Get All Items
    /token_exchange/get_accounts/         =>  Get All Accounts
    /token_exchange/get_transactios/      =>  Get All Transaction
    /token_exchange/transaction_webhook/  =>  Transaction Webhook
    
### :anchor: Token Exchange API (Post Method)
    /token_exchange/link_token/           => Get Plain Link Token
    /token_exchange/get_access_token/     => Plaid-Link-Public_token (exchange public token with access_token)
