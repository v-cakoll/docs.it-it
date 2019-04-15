---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235415"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>I valori di unione Null non risultano visibili nel debugger fino al passaggio successivo

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, i valori impostati tramite un'operazione di unione Null non sono visibili nel debugger immediatamente dopo l'esecuzione dell'operazione di assegnazione quando si usa la versione a 64 bit del framework.|
|Suggerimento|L'esecuzione di un ulteriore passo nel debugger determinerà il corretto aggiornamento del valore locale o del valore del campo. Questo problema è stato corretto in .NET Framework 4.6. L'aggiornamento a questa versione del framework dovrebbe quindi risolvere il problema.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
