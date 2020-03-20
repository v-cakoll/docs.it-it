---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858601"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.|
|Suggerimento|L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo. Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.|
|Scope|Microsoft Edge|
|Versione|4.5|
|Type|Runtime|
