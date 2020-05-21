---
ms.openlocfilehash: 1356f3eee5e2d8090d7d96aafc07a19507a1aff1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721704"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult spostato in Microsoft. AspNetCore. Mvc. Core

`JsonResult`è stato spostato nell' `Microsoft.AspNetCore.Mvc.Core` assembly. Questo tipo è stato usato per essere definito in [Microsoft. AspNetCore. Mvc. Formatters. JSON](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Un attributo a livello di assembly [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) è stato aggiunto a `Microsoft.AspNetCore.Mvc.Formatters.Json` per risolvere questo problema per la maggior parte degli utenti. È possibile che si verifichino problemi nelle app che usano librerie di terze parti.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 6

#### <a name="old-behavior"></a>Comportamento precedente

Un'app che usa una libreria basata su 2,2 è stata compilata correttamente.

#### <a name="new-behavior"></a>Nuovo comportamento

Un'app che usa una libreria basata su 2,2 non riesce a compilare. Viene fornito un errore contenente una variante del testo seguente:

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Per un esempio di questo problema, vedere [DotNet/aspnetcore # 7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Motivo della modifica

Modifiche a livello di piattaforma per la composizione di ASP.NET Core come descritto in [ASPNET/annunciations # 325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Azione consigliata

Potrebbe essere necessario ricompilare le librerie compilate con la versione 2,2 di per `Microsoft.AspNetCore.Mvc.Formatters.Json` risolvere il problema relativo a tutti i consumer. Se interessato, contattare l'autore della libreria. Richiedere la ricompilazione della libreria come destinazione ASP.NET Core 3,0.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
