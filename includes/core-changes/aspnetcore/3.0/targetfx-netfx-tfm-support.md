---
ms.openlocfilehash: ec6724ab378dd614c55a024ede18d997d27be3a3
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79549613"
---
### <a name="target-framework-net-framework-support-dropped"></a>Framework di destinazione: il supporto di .NET Framework è stato eliminato

A partire da ASP.NET Core 3.0, .NET Framework è un framework di destinazione non supportato.

#### <a name="change-description"></a>Descrizione modifica:

.NET Framework 4.8 è l'ultima versione principale di .NET Framework. Le nuove app ASP.NET Core devono essere compilate in .NET Core.New ASP.NET Core apps should be built on .NET Core. A partire dalla versione .NET Core 3.0, è possibile considerare ASP.NET Core 3.0 come parte di .NET Core.

I clienti che utilizzano ASP.NET Core con .NET Framework possono continuare in modo completamente supportato utilizzando la [versione 2.1 LTS](https://dotnet.microsoft.com/download/dotnet-core/2.1). Il supporto e la manutenzione per 2.1 continuano almeno fino al 21 agosto 2021. Questa data è di tre anni dopo la dichiarazione della versione LTS in base ai [criteri di supporto di .NET.](https://dotnet.microsoft.com/platform/support-policy) Il supporto per i pacchetti di ASP.NET Core 2.1 **in .NET Framework** si estenderà all'infinito, in modo simile ai criteri di [manutenzione per altri framework di ASP.NET basati su pacchetti.](https://dotnet.microsoft.com/platform/support/policy/aspnet)

Per ulteriori informazioni sul porting da .NET Framework a .NET Core, vedere [Porting to .NET Core](~/docs/core/porting/index.md).

`Microsoft.Extensions`pacchetti (ad esempio la registrazione, inserimento di dipendenze e configurazione) e Entity Framework Core non sono interessati. Continueranno a supportare .NET Standard.

Per ulteriori informazioni sulla motivazione di questa modifica, vedere [il post di blog originale](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

ASP.NET Core apps could run on either .NET Core or .NET Framework.

#### <a name="new-behavior"></a>Nuovo comportamento

ASP.NET Core apps can only be run on .NET Core.

#### <a name="recommended-action"></a>Azione consigliata

eseguendo una delle operazioni seguenti:

- Mantieni la tua app su ASP.NET Core 2.1.
- Eseguire la migrazione dell'app e delle dipendenze a .NET Core.Migrate your app and dependencies to .NET Core.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
