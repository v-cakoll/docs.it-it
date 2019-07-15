---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858601"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.|
|Suggerimento|L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo. Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

