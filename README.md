# AspNetCore.SEOHelper

Forked package: <a href="https://github.com/esty-c/AspNetCore.SEOHelper" target="_blank">esty-c/AspNetCore.SEOHelper</a>

Forked Nuget package: <a href="https://www.nuget.org/packages/AspNetCore.SEOHelper/">AspNetCore.SEOHelper<a/>
  
Helps to create routing  robots.txt  and sitemap.xml for asp.net core project.

Routing for  <a href="https://codingwithesty.com/search-engine-optimization-library-for-dot-net-code-developers#routingrobotstxt"> robots.txt</a>
  ```csharp
  app.UseRobotsTxt(env.ContentRootPath);
  ```

Routing for <a href="https://codingwithesty.com/search-engine-optimization-library-for-dot-net-code-developers#routesitemapxml">sitemap.xml</a>
```csharp
  app.UseXMLSitemap(env.ContentRootPath);
 ```

Creating SEO friendly URL
```csharp
    string queryString = "Asp.Net MVC Tutorial Part-1";
    var seoQueryString = queryString.ToSEOQueryString();
    var url = $"http://www.example.com/{seoQueryString}";
 ```

How to create sitemap.xml <a href="https://codingwithesty.com/search-engine-optimization-library-for-dot-net-code-developers#createsitemap">click for details</a>

  ```csharp 
            var list = new List<SitemapNode>();
            list.Add(new SitemapNode { LastModified = DateTime.UtcNow, Priority = 0.8, Url = "https://codingwithesty.com/serilog-mongodb-in-asp-net-core", Frequency = SitemapFrequency.Daily });
            list.Add(new SitemapNode { LastModified = DateTime.UtcNow, Priority = 0.8, Url = "https://codingwithesty.com/logging-in-asp-net-core", Frequency = SitemapFrequency.Yearly });

            new SitemapDocument().CreateSitemapXML(list, _env.ContentRootPath);
        
  ```

How to create custom-sitemap-name.xml for multi-language web sites

  ```csharp 
            var list = new List<SitemapNode>();
            list.Add(new SitemapNode { LastModified = DateTime.UtcNow, Priority = 0.8, Url = "https://codingwithesty.com/serilog-mongodb-in-asp-net-core", Frequency = SitemapFrequency.Daily });
            list.Add(new SitemapNode { LastModified = DateTime.UtcNow, Priority = 0.8, Url = "https://codingwithesty.com/logging-in-asp-net-core", Frequency = SitemapFrequency.Yearly });

            new SitemapDocument().CreateSitemapXML(list, _env.ContentRootPath, "sitemap-tr.xml");
        
  ```

Loading Existing sitemap.xml
  ```csharp
List items = new SitemapDocument().LoadFromFile(_env.ContentRootPath);
  ```

Loading Existing custom-sitemap-name.xml
  ```csharp
List items = new SitemapDocument().LoadFromFile(_env.ContentRootPath, "sitemap-tr.xml");
  ```

