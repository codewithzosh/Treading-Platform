#Tables and Relationships

##Users Table

id (Primary Key)
fullName
email
mobile
password
status
isVerified
twoFactorAuth_enabled
twoFactorAuth_sendTo
picture
role
Coins Table

id (Primary Key)
symbol
name
image
current_price
market_cap
market_cap_rank
fully_diluted_valuation
total_volume
high_24h
low_24h
price_change_24h
price_change_percentage_24h
market_cap_change_24h
market_cap_change_percentage_24h
circulating_supply
total_supply
max_supply
ath
ath_change_percentage
ath_date
atl
atl_change_percentage
atl_date
roi
last_updated
Assets Table

id (Primary Key)
quantity
buy_price
coin_id (Foreign Key referencing Coins)
user_id (Foreign Key referencing Users)
Withdrawals Table

id (Primary Key)
status
amount
user_id (Foreign Key referencing Users)
date
Watchlists Table

id (Primary Key)
user_id (Foreign Key referencing Users)
Watchlist_Coins Table (Join Table for many-to-many relationship)

watchlist_id (Foreign Key referencing Watchlists)
coin_id (Foreign Key referencing Coins)
WalletTransactions Table

id (Primary Key)
wallet_id (Foreign Key referencing Wallets)
type
date
transfer_id
purpose
amount
Wallets Table

id (Primary Key)
user_id (Foreign Key referencing Users)
balance
VerificationCodes Table

id (Primary Key)
otp
user_id (Foreign Key referencing Users)
email
mobile
verification_type
TradingHistories Table

id (Primary Key)
selling_price
buying_price
coin_id (Foreign Key referencing Coins)
user_id (Foreign Key referencing Users)
PaymentOrders Table

id (Primary Key)
amount
status
payment_method
user_id (Foreign Key referencing Users)
PaymentDetails Table

id (Primary Key)
account_number
account_holder_name
ifsc
bank_name
user_id (Foreign Key referencing Users)
Orders Table

id (Primary Key)
user_id (Foreign Key referencing Users)
order_type
price
timestamp
status
order_item_id (Foreign Key referencing OrderItems)
OrderItems Table

id (Primary Key)
quantity
coin_id (Foreign Key referencing Coins)
buy_price
sell_price
order_id (Foreign Key referencing Orders)
Notifications Table

id (Primary Key)
from_user_id (Foreign Key referencing Users)
to_user_id (Foreign Key referencing Users)
amount
message
MarketChartData Table

id (Primary Key)
timestamp
price
ForgotPasswordTokens Table

id (Primary Key)
user_id (Foreign Key referencing Users)
otp
verification_type
send_to