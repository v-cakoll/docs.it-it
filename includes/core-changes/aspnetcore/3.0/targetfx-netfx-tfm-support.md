---
ms.openlocfilehash: b60f74947a537c602c7bd1a89587b76bd847c82a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937261"
---
### <a name="target-framework-net-framework-support-dropped"></a>Framework di destinazione: supporto .NET Framework eliminato

A partire da ASP.NET Core 3,0, .NET Framework è un Framework di destinazione non supportato.

#### <a name="change-description"></a>Descrizione delle modifiche

.NET Framework 4,8 è l'ultima versione principale di .NET Framework. Le nuove app ASP.NET Core devono essere compilate in .NET Core. A partire dalla versione di .NET Core 3,0, è possibile pensare a ASP.NET Core 3,0 come parte di .NET Core.

I clienti che usano ASP.NET Core con .NET Framework possono continuare in modo completamente supportato usando la [versione LTS 2,1](https://www.microsoft.com/net/download/dotnet-core/2.1). Il supporto e la manutenzione per 2,1 continuano fino ad almeno il 21 agosto 2021. Questa data è di tre anni dopo la dichiarazione della versione LTS per i [criteri di supporto .NET](https://www.microsoft.com/net/platform/support-policy). Il supporto per i pacchetti ASP.NET Core 2,1 **in .NET Framework** si estenderà a tempo indefinito, in modo analogo ai [criteri di manutenzione per altri framework ASP.NET basati su pacchetti](https://dotnet.microsoft.com/platform/support/policy/aspnet).

Per altre informazioni sul porting da .NET Framework a .NET Core, vedere [porting to .NET Core](~/docs/core/porting/index.md).

i pacchetti `Microsoft.Extensions` (ad esempio registrazione, inserimento di dipendenze e configurazione) e Entity Framework Core non sono interessati. Continueranno a supportare .NET Standard.

Per ulteriori informazioni sulla motivazione di questa modifica, vedere [il post di Blog originale](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

ASP.NET Core app possono essere eseguite in .NET Core o .NET Framework.

#### <a name="new-behavior"></a>Nuovo comportamento

ASP.NET Core app possono essere eseguite solo in .NET Core.

#### <a name="recommended-action"></a>Azione consigliata

Eseguire una delle azioni seguenti:

- Mantieni l'app ASP.NET Core 2,1.
- Eseguire la migrazione dell'app e delle dipendenze a .NET Core.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuna

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
