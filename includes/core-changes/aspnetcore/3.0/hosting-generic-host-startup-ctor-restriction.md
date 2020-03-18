---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901821"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Hosting: l'host generico limita l'inserimento del costruttore di avvioHosting: Generic host restricts Startup constructor injection

Gli unici tipi supportati dall'host generico `Startup` per l'inserimento del costruttore di classe `IHostEnvironment`sono , `IWebHostEnvironment`, e `IConfiguration`. Le `WebHost` app in uso non sono interessate.

#### <a name="change-description"></a>Descrizione modifica:

Prima di ASP.NET Core 3.0, l'inserimento del `Startup` costruttore poteva essere utilizzato per tipi arbitrari nel costruttore della classe. In ASP.NET Core 3.0, lo stack Web è stato nuovamente reindirizzato alla libreria host generica. È possibile visualizzare la modifica nel file *Program.cs* dei modelli:

**ASP.NET Core 2.x:**

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3.0:**

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host`utilizza un contenitore di inserimento delle dipendenze (DI) per compilare l'app. `WebHost`utilizza due contenitori: uno per l'host e uno per l'app. Di conseguenza, `Startup` il costruttore non supporta più l'inserimento di servizi personalizzato. Solo `IHostEnvironment` `IWebHostEnvironment`, `IConfiguration` , e può essere iniettato. Questa modifica impedisce problemi DI, ad esempio la creazione duplicata di un servizio singleton.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è una conseguenza del replatforming dello stack Web nella libreria host generica.

#### <a name="recommended-action"></a>Azione consigliata

Inserire i `Startup.Configure` servizi nella firma del metodo. Ad esempio:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
