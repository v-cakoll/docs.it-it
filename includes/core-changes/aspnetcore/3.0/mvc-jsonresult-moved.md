---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901963"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult spostato in Microsoft.AspNetCore.Mvc.Core

`JsonResult`è stato `Microsoft.AspNetCore.Mvc.Core` spostato nell'assieme. Questo tipo utilizzato per essere definito in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Un attributo di livello di assembly [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) è stato aggiunto per `Microsoft.AspNetCore.Mvc.Formatters.Json` risolvere questo problema per la maggior parte degli utenti. Le app che utilizzano librerie di terze parti potrebbero riscontrare problemi.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 6

#### <a name="old-behavior"></a>Comportamento precedente

Un'app che usa una libreria basata su 2.2 viene compilata correttamente.

#### <a name="new-behavior"></a>Nuovo comportamento

Una app che usa una libreria basata su 2.2 non riesce la compilazione. Viene fornito un errore contenente una variazione del testo seguente:

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Per un esempio di tale problema, vedere [dotnet/aspnetcore-7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Motivo della modifica

Modifiche a livello di piattaforma per la composizione di ASP.NET Core come descritto in [aspnet/Announcements.325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Azione consigliata

Le librerie compilate con `Microsoft.AspNetCore.Mvc.Formatters.Json` la versione 2.2 di potrebbero essere necessarie per ricompilare per risolvere il problema per tutti i consumer. Se interessato, contattare l'autore della libreria. Richiedere la ricompilazione della libreria come destinazione ASP.NET Core 3.0.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
