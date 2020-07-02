---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617250"
---
### <a name="workflow-30-types-are-obsolete"></a>I tipi di WorkFlow 3.0 sono obsoleti

#### <a name="details"></a>Dettagli

Le API Windows Workflow Foundation (WWF) 3.0 (dallo spazio dei nomi System.Workflow) sono obsolete.

#### <a name="suggestion"></a>Suggerimento

È ora necessario usare le nuove API WWF 4.0 (in System. Activities). Un esempio di uso delle nuove API è disponibile [qui](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) e altre indicazioni sono disponibili [qui](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5). In alternativa, dato che le API WWF 3.0 sono ancora supportate, è possibile usarle ed evitare l'avviso in fase di compilazione, eliminandolo o usando un compilatore precedente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.5         |
| Type    | Ridestinazione |
