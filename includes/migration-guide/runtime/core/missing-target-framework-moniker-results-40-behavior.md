---
ms.openlocfilehash: 29b8feb7959c718391b963c8402b97351b93fa49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235785"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Comportamento 4.0 a causa della mancanza del moniker del framework di destinazione

|   |   |
|---|---|
|Dettagli|Le applicazioni senza un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> applicato a livello di assembly verranno eseguite automaticamente con la semantica (non standard) di .NET Framework 4.0. Per garantire un livello di qualità elevato, è consigliabile applicare a tutti i file binari in modo esplicito un attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> che indica la versione di .NET Framework con cui sono stati compilati. Si noti che l'uso di un moniker del framework di destinazione in un file di progetto causerà l'applicazione automatica di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> da MSBuild.|
|Suggerimento|È consigliabile specificare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> aggiungendo direttamente l'attributo all'assembly oppure specificando un framework di destinazione nel [file di progetto o tramite l'interfaccia utente grafica delle proprietà del progetto di Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
