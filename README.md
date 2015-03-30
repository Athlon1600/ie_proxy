# ie_proxy
A tiny C++ library that provides a simple API for querying **Internet Proxy Settings.**
Unlike other libraries that set and retrieve proxy settings using registry, this one communicates directly
with Windows API.


![alt](http://i.imgur.com/yzzt7qH.png) ![alt](http://i.imgur.com/d3ESwNX.png)
## Usage

```C++

#pragma comment(lib, "IEProxy.lib");

#include "IEProxy.h";

using namespace ie_proxy;

int main(){

	ProxyConfig pc;

	// pc.auto_config_url = L"http://www.proxynova.com/proxy.pac";
	// pc.auto_detect_settings = true;
	// pc.bypass_domain_list = L"google.com; yahoo.com; bing.com;";
	pc.proxy_server = L"124.88.67.40:8080";
	
	// change proxy settings
	setProxyConfig(&pc);
	
	ProxyConfig pc2;
	
	// retrieve current proxy settings
	getProxyConfig(&pc2);
	
	//std::wcout << pc2.proxy_server << endl;

	return 0;
}

```

http://support.microsoft.com/kb/226473
