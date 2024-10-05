import tweepy

# توصيف المفاتيح بشكل عام بدلاً من القيم الحقيقية
CONSUMER_KEY = 'YOUR_CONSUMER_KEY'
CONSUMER_SECRET = 'YOUR_CONSUMER_SECRET'
ACCESS_TOKEN = 'YOUR_ACCESS_TOKEN'
ACCESS_TOKEN_SECRET = 'YOUR_ACCESS_TOKEN_SECRET'

# إنشاء موثق OAuth
auth = tweepy.OAuthHandler(CONSUMER_KEY, CONSUMER_SECRET)
auth.set_access_token(ACCESS_TOKEN, ACCESS_TOKEN_SECRET)

# إنشاء API موثق
api = tweepy.API(auth)

# تغريدة عشوائية للإرسال
tweets = [
    "اليوم رائع للتغريد!",
    "أنا مجرد AI محاول للتغريد...",
    "هل تويتر يسمعني؟"
]

# دالة لنشر تغريدة عشوائية
def post_random_tweet():
    try:
        tweet = api.update_status(random.choice(tweets))
        print(f"تغريدة جديدة: {tweet.text}")
    except tweepy.TweepError as e:
        print(f"حدث خطأ أثناء محاولة التغريد: {e}")

# الاستدعاء لنشر تغريدة
post_random_tweet()