---
ms.openlocfilehash: 58b1190e3e6a3168d35700eed655f6756e076a29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901827"
---
### <a name="mvc-async-suffix-trimmed-from-controller-action-names"></a>MVC: suffisso asincrono tagliato dai nomi delle azioni del controller

Come parte dell'indirizzamento di [dotnet/aspnetcore-4849](https://github.com/dotnet/aspnetcore/issues/4849) `Async` , ASP.NET Core MVC taglia il suffisso dai nomi delle azioni per impostazione predefinita. A partire da ASP.NET Core 3.0, questa modifica influisce sia sul routing che sulla generazione dei collegamenti.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Si consideri il seguente controller DI MVC ASP.NET Core:

```csharp
public class ProductController : Controller
{
    public async IActionResult ListAsync()
    {
        var model = await DbContext.Products.ToListAsync();
        return View(model);
    }
}
```

L'azione è `Product/ListAsync`instradabile tramite . La generazione dei `Async` collegamenti richiede la specifica del suffisso. Ad esempio:

```cshtml
<a asp-controller="Product" asp-action="ListAsync">List</a>
```

#### <a name="new-behavior"></a>Nuovo comportamento

In ASP.NET Core 3.0, l'azione è instradabile tramite `Product/List`. Il codice di generazione `Async` del collegamento deve omettere il suffisso. Ad esempio:

```cshtml
<a asp-controller="Product" asp-action="List">List</a>
```

Questa modifica non influisce sui `[ActionName]` nomi specificati utilizzando l'attributo . Il nuovo comportamento può `MvcOptions.SuppressAsyncSuffixInActionNames` essere `false` `Startup.ConfigureServices`disabilitato impostando su in :

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="reason-for-change"></a>Motivo della modifica

Per convenzione, i metodi .NET asincroni sono suffissi con `Async`. Tuttavia, quando un metodo definisce un'azione MVC, `Async` è indesiderabile utilizzare il suffisso.

#### <a name="recommended-action"></a>Azione consigliata

Se l'app dipende da azioni MVC `Async` che conservano il suffisso del nome, scegli una delle seguenti attenuazioni:

- Utilizzare `[ActionName]` l'attributo per mantenere il nome originale.
- Disattivare completamente la `MvcOptions.SuppressAsyncSuffixInActionNames` ridenominazione impostando su `false` in `Startup.ConfigureServices`:

```csharp
services.AddMvc(options =>
{
   options.SuppressAsyncSuffixInActionNames = false;
});
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
