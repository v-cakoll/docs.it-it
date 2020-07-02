---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620254"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Comportamento 4.0 a causa della mancanza del moniker del framework di destinazione

#### <a name="details"></a>Dettagli

Le applicazioni senza un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applicato a livello di assembly verranno eseguite automaticamente con la semantica (non standard) di .NET Framework 4.0. Per garantire un livello di qualità elevato, è consigliabile applicare a tutti i file binari in modo esplicito un attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> che indica la versione di .NET Framework con cui sono stati compilati. Si noti che l'uso di un moniker del framework di destinazione in un file di progetto causerà l'applicazione automatica di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> da MSBuild.

#### <a name="suggestion"></a>Suggerimento

È consigliabile specificare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> aggiungendo direttamente l'attributo all'assembly oppure specificando un framework di destinazione nel [file di progetto o tramite l'interfaccia utente grafica delle proprietà del progetto di Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.5|
|Type|Runtime|
