require 'savon/mock/spec_helper'
=> true
[20] pry(main)> include Savon::SpecHelper
=> Object
[21] pry(main)> savon.mock!
=> [#<Savon::SpecHelper::Interface:0x007fa16e0fae08>]
[22] pry(main)> savon.expects(:QueryLov).with(message: :any).returns(File.read("#{::Rails.root}/spec/fixtures/pms/responses/opera/address_types.xml"))
=> #<Savon::MockExpectation:0x007fa16c433e28
 @actual=nil,
 @expected={:operation_name=>:QueryLov, :message=>:any},
 @response=
  {:code=>200,
   :headers=>{},
   :body=>
    "<?xml version=\"1.0\" encoding=\"utf-8\"?><soap:Envelope xmlns:soap=\"http://schemas.xmlsoap.org/soap/envelope/\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xmlns:xsd=\"http://www.w3.org/2001/XMLSchema\" xmlns:wsa=\"http://schemas.xmlsoap.org/ws/2004/08/addressing\"><soap:Header><OGHeader transactionID=\"1472634714\" timeStamp=\"2016-08-31T11:11:54.532+02:00\" primaryLangID=\"E\" channelValidation=\"true\" xmlns=\"http://webservices.micros.com/og/4.3/Core/\"><Origin entityID=\"KIOSK\" systemType=\"PMS\" /><Destination entityID=\"KIOSK\" systemType=\"KIOSK\" /><Authentication><UserCredentials><UserName>KIOSK</UserName><UserPassword>$$$KIOSK$$</UserPassword><Domain>UCAN</Domain></UserCredentials></Authentication></OGHeader><wsa:Action>http://webservices.micros.com/ows/5.1/Information.wsdl#QueryLovResponse</wsa:Action><wsa:MessageID>urn:uuid:a5c31fc7-34b6-4367-bbfe-8adf3895d2bd</wsa:MessageID><wsa:RelatesTo>urn:uuid:18e1fce9-5640-4d1f-8de2-62d301380335</wsa:RelatesTo><wsa:To>http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</wsa:To></soap:Header><soap:Body><LovResponse xmlns:hc=\"http://webservices.micros.com/og/4.3/HotelCommon/\" xmlns:c=\"http://webservices.micros.com/og/4.3/Core/\" xmlns=\"http://webservices.micros.com/ows/5.1/Information.wsdl\"><Result resultStatusFlag=\"SUCCESS\" /><LovQueryResult><LovValue description=\"Home Address\">HOME</LovValue><LovValue description=\"Other Address\">OTHER</LovValue><LovValue description=\"Business Address\">BUSINESS</LovValue><LovValue description=\"Billing Address\">BILLING</LovValue><LovValue description=\"Shipping Address\">SHIPPING</LovValue><LovValue description=\"Contract Address\">CONTRACT</LovValue><LovValue description=\"AR Address\">AR ADDRESS</LovValue><LovValue description=\"Protected Address\">PROTECTED</LovValue></LovQueryResult></LovResponse></soap:Body></soap:Envelope>\n"}>
[23] pry(main)> savon.expects(:QueryLov).with(message: :any).returns(File.read("#{::Rails.root}/spec/fixtures/pms/responses/opera/add[23] pry(main)> PMS::Requests::VenueConfiguration::Opera.new(Venue.first).address_types
  Venue Load (1.0ms)  SELECT  "venues".* FROM "venues"  ORDER BY "venues"."id" ASC LIMIT 1
  PmsAuthCredential Load (0.3ms)  SELECT  "pms_auth_credentials".* FROM "pms_auth_credentials" WHERE "pms_auth_credentials"."venue_id" = $1 LIMIT 1  [["venue_id", 1]]
  Rendered lib/pms/templates/opera/lov_request.xml.erb (5.4ms)
OPERA SOAP REQUEST: ID(1472645674) | 2016-08-31 14:14:34 +0200 | Querylov
=> {:result=>{:@result_status_flag=>"SUCCESS"},
 :lov_query_result=>{:lov_value=>["HOME", "OTHER", "BUSINESS", "BILLING", "SHIPPING", "CONTRACT", "AR ADDRESS", "PROTECTED"]},
 :"@xmlns:hc"=>"http://webservices.micros.com/og/4.3/HotelCommon/",
 :"@xmlns:c"=>"http://webservices.micros.com/og/4.3/Core/",
 :@xmlns=>"http://webservices.micros.com/ows/5.1/Information.wsdl"}
[24] pry(main)>
