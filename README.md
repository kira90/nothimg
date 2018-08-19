api_id = APIID
api_hash = 'APIHASH'
client = TelegramClient('session_name', api_id, api_hash)
client.start()
print(client.get_me().stringify())
# client.send_message('username', 'Hello! Talking to you from Telethon')
# client.send_file('username', '/home/myself/Pictures/holidays.jpg')
# client.download_profile_photo('hamidzr')
messages = client.get_messages('intothestates', limit=2000)
print(len(messages))
for msg in tqdm(messages):
client.download_media(msg)
