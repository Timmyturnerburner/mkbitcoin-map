# mkbitcoin-map
require 'uri' require 'net/http' require 'openssl'  url = URI("https://circleci.com/api/v2/schedule/%7Bschedule-id%7D")  http = Net::HTTP.new(url.host, url.port) http.use_ssl = true http.verify_mode = OpenSSL::SSL::VERIFY_NONE  request = Net::HTTP::Delete.new(url) request["authorization"] = 'Basic REPLACE_BASIC_AUTH'  response = http.request(request) puts response.read_body
