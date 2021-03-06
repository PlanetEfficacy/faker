# Faker::Internet

```ruby
# Optional argument name=nil
Faker::Internet.email #=> "eliza@mann.net"

Faker::Internet.email('Nancy') #=> "nancy@terry.biz"

# Optional argument name=nil
Faker::Internet.free_email #=> "freddy@gmail.com"

Faker::Internet.free_email('Nancy') #=> "nancy@yahoo.com"

# Optional argument name=nil
Faker::Internet.safe_email #=> "christelle@example.org"

Faker::Internet.safe_email('Nancy') #=> "nancy@example.net"

# Optional arguments specifier=nil, separators=%w(. _)
Faker::Internet.user_name #=> "alexie"

Faker::Internet.user_name('Nancy') #=> "nancy"

Faker::Internet.user_name('Nancy Johnson', %w(. _ -)) #=> "johnson-nancy"

# Optional arguments: min_length=8, max_length=16
Faker::Internet.password #=> "vg5msvy1uerg7"

Faker::Internet.password(8) #=> "yfgjik0hgzdqs0"

Faker::Internet.password(10, 20) #=> "eoc9shwd1hwq4vbgfw"

Faker::Internet.password(10, 20, true) #=> "3k5qS15aNmG"

Faker::Internet.password(10, 20, true, true) #=> "*%NkOnJsH4"

Faker::Internet.domain_name #=> "effertz.info"

Faker::Internet.fix_umlauts('äöüß') #=> "aeoeuess"

Faker::Internet.domain_word #=> "haleyziemann"

Faker::Internet.domain_suffix #=> "info"

Faker::Internet.ip_v4_address #=> "24.29.18.175"

# Private IP range according to RFC 1918 and 127.0.0.0/8 and 169.254.0.0/16.
Faker::Internet.private_ip_v4_address #=> "10.0.0.1"

# Guaranteed not to be in the ip range from the private_ip_v4_address method.
Faker::Internet.public_ip_v4_address #=> "24.29.18.175"

Faker::Internet.ip_v4_cidr #=> "24.29.18.175/21"

Faker::Internet.ip_v6_address #=> "ac5f:d696:3807:1d72:2eb5:4e81:7d2b:e1df"

Faker::Internet.ip_v6_cidr #=> "ac5f:d696:3807:1d72:2eb5:4e81:7d2b:e1df/78"

# Optional argument prefix=''
Faker::Internet.mac_address #=> "e6:0d:00:11:ed:4f"
Faker::Internet.mac_address('55:44:33') #=> "55:44:33:02:1d:9b"

# Optional arguments: host=domain_name, path="/#{user_name}"
Faker::Internet.url #=> "http://thiel.com/chauncey_simonis"
Faker::Internet.url('example.com') #=> "http://example.com/clotilde.swift"
Faker::Internet.url('example.com', '/foobar.html') #=> "http://example.com/foobar.html"

# Optional arguments: words=nil, glue=nil
Faker::Internet.slug #=> "pariatur_laudantium"
Faker::Internet.slug('foo bar') #=> "foo.bar"
Faker::Internet.slug('foo bar', '-') #=> "foo-bar"

# Omniauth is a library that standardizes multi-provider authentication for web applications.
# Each of the following methods will return a randomized hash that mimics
# the hash returned by each of these omniauth strategies.
Faker::Internet::Omniauth.google #=>
# {
#   :provider => "google_oauth2",
#   :uid => "123456789",
#   :info => {
#     :name => "John Doe",
#     :email => "john@company_name.com",
#     :first_name => "John",
#     :last_name => "Doe",
#     :image => "https://lh3.googleusercontent.com/url/photo.jpg"
#   },
#   :credentials => {
#       :token => "token",
#       :refresh_token => "another_token",
#       :expires_at => 1354920555,
#       :expires => true
#   },
#   :extra => {
#     :raw_info => {
#       :sub => "123456789",
#       :email => "user@domain.example.com",
#       :email_verified => true,
#       :name => "John Doe",
#       :given_name => "John",
#       :family_name => "Doe",
#       :profile => "https://plus.google.com/123456789",
#       :picture => "https://lh3.googleusercontent.com/url/photo.jpg",
#       :gender => "male",
#       :birthday => "0000-06-25",
#       :locale => "en",
#       :hd => "company_name.com"
#     },
#     :id_info => {
#       "iss" => "accounts.google.com",
#       "at_hash" => "HK6E_P6Dh8Y93mRNtsDB1Q",
#       "email_verified" => "true",
#       "sub" => "10769150350006150715113082367",
#       "azp" => "APP_ID",
#       "email" => "jsmith@example.com",
#       "aud" => "APP_ID",
#       "iat" => 1353601026,
#       "exp" => 1353604926,
#       "openid_id" => "https://www.google.com/accounts/o8/id?id=ABCdfdswawerSDFDsfdsfdfjdsf"
#     }
#   }
# }
Faker::Internet::Omniauth.facebook #=>
# {
#   provider: 'facebook',
#   uid: '1234567',
#   info: {
#     email: 'joe@bloggs.com',
#     name: 'Joe Bloggs',
#     first_name: 'Joe',
#     last_name: 'Bloggs',
#     image: 'http://graph.facebook.com/1234567/picture?type=square',
#     verified: true
#   },
#   credentials: {
#     token: 'ABCDEF...',
#     expires_at: 1321747205,
#     expires: true
#   },
#   extra: {
#     raw_info: {
#       id: '1234567',
#       name: 'Joe Bloggs',
#       first_name: 'Joe',
#       last_name: 'Bloggs',
#       link: 'http://www.facebook.com/jbloggs',
#       username: 'jbloggs',
#       location: { id: '123456789', name: 'Palo Alto, California' },
#       gender: 'male',
#       email: 'joe@bloggs.com',
#       timezone: -8,
#       locale: 'en_US',
#       verified: true,
#       updated_time: '2011-11-11T06:21:03+0000',
#     }
#   }
# }
Faker::Internet::Omniauth.twitter #=>
# {
#   :provider => "twitter",
#   :uid => "123456",
#   :info => {
#     :nickname => "johnqpublic",
#     :name => "John Q Public",
#     :location => "Anytown, USA",
#     :image => "http://si0.twimg.com/sticky/default_profile_images/default_profile_2_normal.png",
#     :description => "a very normal guy.",
#     :urls => {
#       :Website => nil,
#       :Twitter => "https://twitter.com/johnqpublic"
#     }
#   },
#   :credentials => {
#     :token => "a1b2c3d4...", # The OAuth 2.0 access token
#     :secret => "abcdef1234"
#   },
#   :extra => {
#     :access_token => "", # An OAuth::AccessToken object
#     :raw_info => {
#       :name => "John Q Public",
#       :listed_count => 0,
#       :profile_sidebar_border_color => "181A1E",
#       :url => nil,
#       :lang => "en",
#       :statuses_count => 129,
#       :profile_image_url => "http://si0.twimg.com/sticky/default_profile_images/default_profile_2_normal.png",
#       :profile_background_image_url_https => "https://twimg0-a.akamaihd.net/profile_background_images/229171796/pattern_036.gif",
#       :location => "Anytown, USA",
#       :time_zone => "Chicago",
#       :follow_request_sent => false,
#       :id => 123456,
#       :profile_background_tile => true,
#       :profile_sidebar_fill_color => "666666",
#       :followers_count => 1,
#       :default_profile_image => false,
#       :screen_name => "",
#       :following => false,
#       :utc_offset => -3600,
#       :verified => false,
#       :favourites_count => 0,
#       :profile_background_color => "1A1B1F",
#       :is_translator => false,
#       :friends_count => 1,
#       :notifications => false,
#       :geo_enabled => true,
#       :profile_background_image_url => "http://twimg0-a.akamaihd.net/profile_background_images/229171796/pattern_036.gif",
#       :protected => false,
#       :description => "a very normal guy.",
#       :profile_link_color => "2FC2EF",
#       :created_at => "Thu Jul 4 00:00:00 +0000 2013",
#       :id_str => "123456",
#       :profile_image_url_https => "https://si0.twimg.com/sticky/default_profile_images/default_profile_2_normal.png",
#       :default_profile => false,
#       :profile_use_background_image => false,
#       :entities => {
#         :description => {
#           :urls => []
#         }
#       },
#       :profile_text_color => "666666",
#       :contributors_enabled => false
#     }
#   }
# }

Faker::Internet::Omniauth.linkedin #=>
# {
#   "provider"=>"linkedin",
#   "uid"=>"AbC123",
#   "info"=> {
#     "name"=>"John Doe",
#     "email"=>"john@doe.com",
#     "nickname"=>"John Doe",
#     "first_name"=>"John",
#     "last_name"=>"Doe",
#     "location"=>"Greater Boston Area, US",
#     "description"=>"Senior Developer, Hammertech",
#     "image"=> "http://m.c.lnkd.licdn.com/mpr/mprx/0_aBcD...",
#     "phone"=>"null",
#     "headline"=> "Senior Developer, Hammertech",
#     "industry"=>"Internet",
#     "urls"=>{
#       "public_profile"=>"http://www.linkedin.com/in/johndoe"
#     }
#   },
#   "credentials"=> {
#     "token"=>"12312...",
#     "secret"=>"aBc..."
#   },
#   "extra"=>
#   {
#     "access_token"=> {
#       "token"=>"12312...",
#       "secret"=>"aBc...",
#       "consumer"=>nil, #<OAuth::Consumer>
#       "params"=> {
#         :oauth_token=>"12312...",
#         :oauth_token_secret=>"aBc...",
#         :oauth_expires_in=>"5183999",
#         :oauth_authorization_expires_in=>"5183999",
#       },
#       "response"=>nil #<Net::HTTPResponse>
#     },
#    "raw_info"=> {
#      "firstName"=>"Joe",
#      "headline"=>"Senior Developer, Hammertech",
#      "id"=>"AbC123",
#      "industry"=>"Internet",
#      "lastName"=>"Doe",
#      "location"=> {"country"=>{"code"=>"us"}, "name"=>"Greater Boston Area"},
#      "pictureUrl"=> "http://m.c.lnkd.licdn.com/mpr/mprx/0_aBcD...",
#      "publicProfileUrl"=>"http://www.linkedin.com/in/johndoe"
#     }
#   }
# }

```
