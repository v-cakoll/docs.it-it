---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617192"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>La versione di Entity Framework deve corrispondere alla versione di .NET Framework

#### <a name="details"></a>Dettagli

La versione di Entity Framework (EF) deve corrispondere alla versione .NET Framework. Per .NET Framework 4.5 è consigliato Entity Framework 5. Esistono alcuni problemi noti con Entity Framework 4.x in un progetto .NET Framework 4.5 in relazione a <xref:System.ComponentModel.DataAnnotations>. In .NET Framework 4,5 questi elementi sono stati spostati in un assembly diverso, pertanto si verificano problemi di individuazione delle annotazioni da utilizzare.

#### <a name="suggestion"></a>Suggerimento

Eseguire l'aggiornamento a Entity Framework 5 per .NET Framework 4.5

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.5         |
| Type    | Ridestinazione |
