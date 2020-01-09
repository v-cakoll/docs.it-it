---
ms.openlocfilehash: 4f2ace670884d154b219d2146a242d2cee098831
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344292"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult spostato in Microsoft. AspNetCore. Mvc. Core

`JsonResult` è stato spostato nell'assembly `Microsoft.AspNetCore.Mvc.Core`. Questo tipo è stato usato per essere definito in [Microsoft. AspNetCore. Mvc. Formatters. JSON](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json). Un attributo a livello di assembly [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) è stato aggiunto al `Microsoft.AspNetCore.Mvc.Formatters.Json` per risolvere questo problema per la maggior parte degli utenti. È possibile che si verifichino problemi nelle app che usano librerie di terze parti.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 6

#### <a name="old-behavior"></a>Comportamento precedente

Un'app che usa una libreria basata su 2,2 è stata compilata correttamente.

#### <a name="new-behavior"></a>Nuovo comportamento

Un'app che usa una libreria basata su 2,2 non riesce a compilare. Viene fornito un errore contenente una variante del testo seguente:

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Per un esempio di questo problema, vedere [ASPNET/AspNetCore # 7220](https://github.com/aspnet/AspNetCore/issues/7220).

#### <a name="reason-for-change"></a>Motivo della modifica

Modifiche a livello di piattaforma per la composizione di ASP.NET Core come descritto in [ASPNET/annunciations # 325](https://github.com/aspnet/Announcements/issues/325).

#### <a name="recommended-action"></a>Azione consigliata

Per risolvere il problema relativo a tutti i consumer, potrebbe essere necessario ricompilare le librerie compilate con la versione 2,2 di `Microsoft.AspNetCore.Mvc.Formatters.Json`. Se interessato, contattare l'autore della libreria. Richiedere la ricompilazione della libreria come destinazione ASP.NET Core 3,0.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
