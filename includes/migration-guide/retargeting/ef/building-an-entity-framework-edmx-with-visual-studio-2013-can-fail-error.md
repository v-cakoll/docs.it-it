---
ms.openlocfilehash: c5099f610569f7788bb829a2153006d20d8a4ea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615687"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>La compilazione di un file edmx di Entity Framework con Visual Studio 2013 può avere esito negativo con errore MSB4062 se si usano le attività EntityDeploySplit o EntityClean

#### <a name="details"></a>Dettagli

Gli strumenti di MSBuild 12.0 (inclusi in Visual Studio 2013) hanno modificato i percorsi dei file MSBuild, invalidando i vecchi file di destinazioni di Entity Framework. Il risultato è che le attività `EntityDeploySplit` e `EntityClean` hanno esito negativo perché non sono in grado di trovare `Microsoft.Data.Entity.Build.Tasks.dll`. Si noti che questo problema è causato da una modifica del set di strumenti (MSBuild/VS) e non da una modifica di .NET Framework. Si verificherà solo quando si aggiornano gli strumenti di sviluppo, e non aggiornando semplicemente .NET Framework.

#### <a name="suggestion"></a>Suggerimento

I file di destinazioni di Entity Framework sono stati corretti per supportare il nuovo layout MSBuild a partire da .NET Framework 4.6. L'aggiornamento a tale versione di .NET Framework consentirà di risolvere questo problema. È possibile anche usare [questa soluzione alternativa](https://stackoverflow.com/a/24249247/131944) per applicare direttamente una patch ai file di destinazione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.5.1       |
| Type    | Ridestinazione |
