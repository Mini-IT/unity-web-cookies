# Unity WebGL Cookies

This package for Unity allows you to access web cookies in WebGL applications.

The source is based on [UnityWebGLCookie](https://github.com/VegK/UnityWebGLCookie) by Eugene Lobashev

## Installation

Use Unity Package Manager to [add](https://docs.unity3d.com/Manual/upm-ui-giturl.html) this package using this URL:  `https://github.com/Mini-IT/unity-web-cookies`

## Usage

```scharp
using MiniIT;
using UnityEngine;

public class Example
{
	public void DoSomethingWithCookies()
	{
		// Get a cookie by name
		string value = HttpCookie.GetCookie("some.cookie.name");

		// Set a cookie
		HttpCookie.SetCookie("another.cookie", "another.value");

		PrintAllCookies();
		
		HttpCookie.RemoveCookie("another.cookie");
	}

	public void PrintAllCookies()
	{
		Dictionary<string, string> all = HttpCookie.GetAllCookies();
		foreach (var pair in all)
		{
			Debug.Log($"Cookie: {pair.Key} = {pair.Value}");
		}
	}
}
```

