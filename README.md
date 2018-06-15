# NaverMap

[![Gem Version](https://badge.fury.io/rb/naver_map.svg)](https://badge.fury.io/rb/naver_map)
[![Build Status](https://travis-ci.org/say8425/naver_map_ruby.svg?branch=master)](https://travis-ci.org/say8425/naver_map_ruby)

This is ruby gem for using Naver Map API.

## Installation

Add this line to your application's Gemfile:  //응용 프로그램의 Gemfile에 이 줄을 추가합니다.

```ruby
gem 'naver_map'
```

And then execute: 

    $ bundle

Or install it yourself as:  //또는 사용자가 직접 설치

    $ gem install naver_map

## Usage

```ruby
require 'naver_map'

city_hall = NaverMap.new('input your client id', 'input your client secret')
```

First you need to confirm your Naver API client id and client secret key. You can confirm it at [Naver Developer Application page](https://developers.naver.com/appinfo).  
//먼저 네이버 API클라이언트 ID와 고객 비밀 키를 확인해야 합니다. [네이버 개발자 응용 프로그램]에서 확인할 수 있습니다.
Then you can initialize `naver_map` with your client id and client secret key. 
//그런 다음 클라이언트 ID와 클라이언트 비밀 키를 사용하여 naver_map을 초기화할 수 있습니다.

### Getting coordinates with address 
 
```ruby
city_hall.address_to_coordinates('서울특별시 중구 세종대로 110 서울특별시청')
=> {:x=>126.9783882, :y=>37.5666103} 
```
The address will be converted into coordinates and returned. But coordinates can be plural.
In this case, coordinates will be returned in array. And when your address is not clear,
then this case occurred frequently. For example your address parameter is
'서울특별시 중구'. Then you'll get many coordinates values.
//주소가 좌표로 변환되어 반환됩니다. 그러나 좌표는 복수형일 수 있다.
이 경우 좌표가 배열로 반환됩니다. 그리고 당신의 주소가 확실하지 않을 때,
그리고 이 사건은 자주 일어났다. 예를 들어, 주소 매개 변수는
서울 역입니다. 그러면 많은 좌표 값이 표시됩니다.

### Getting address with coordinates

```ruby
city_hall.coordinates_to_address(126.9783882, 37.5666103)
=> ["서울특별시 중구 태평로1가 31", "서울특별시 중구 세종대로 110 서울시청"]
```

The coordinates will be converted into address. And address also can be can be plural.
//좌표가 주소로 변환됩니다. 주소는 복수형일 수도 있습니다.

## Contributing

Bug reports and pull requests are welcome.

## License

MIT
