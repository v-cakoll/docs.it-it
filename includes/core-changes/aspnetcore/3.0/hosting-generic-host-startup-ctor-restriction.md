---
ms.openlocfilehash: be9a79f6ead3e72d7ffaade758704f0c1e2477f0
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394142"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a>Hosting: l'host generico limita l'inserimento del costruttore di avvio

Gli unici tipi supportati dall'host generico per l'inserimento di un costruttore di classe `Startup` sono `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`. Le app che usano `WebHost` non sono interessate.

#### <a name="change-description"></a>Descrizione della modifica

Prima di ASP.NET Core 3,0, era possibile usare l'inserimento del costruttore per i tipi arbitrari nel costruttore della classe `Startup`. In ASP.NET Core 3,0, lo stack Web è stato riplatformato nella libreria host generica. È possibile visualizzare le modifiche apportate al file *Program.cs* dei modelli:

**ASP.NET Core 2. x:**

<https://github.com/aspnet/AspNetCore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

**ASP.NET Core 3,0:**

<https://github.com/aspnet/AspNetCore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

`Host` usa un contenitore DI inserimento delle dipendenze per compilare l'app. `WebHost` usa due contenitori: uno per l'host e uno per l'app. Di conseguenza, il costruttore `Startup` non supporta più l'inserimento di un servizio personalizzato. È possibile inserire solo `IHostEnvironment`, `IWebHostEnvironment` e `IConfiguration`. Questa modifica impedisce problemi DI inserimento, ad esempio la creazione di duplicati di un servizio singleton.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica è una conseguenza della ripiattaforma dello stack Web nella libreria host generica.

#### <a name="recommended-action"></a>Azione consigliata

Inserire i servizi nella firma del metodo `Startup.Configure`. Esempio:

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
