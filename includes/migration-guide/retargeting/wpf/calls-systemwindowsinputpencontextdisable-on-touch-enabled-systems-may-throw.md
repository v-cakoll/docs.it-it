---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617536"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Le chiamate a System.Windows.Input.PenContext.Disable nei sistemi abilitati per il tocco possono generare ArgumentException

#### <a name="details"></a>Dettagli

In alcuni casi, le chiamate al metodo **System.Windows.Intput.PenContext.Disable** interno nei sistemi abilitati per il tocco possono generare una `T:System.ArgumentException` non gestita a causa della reentrancy.

#### <a name="suggestion"></a>Suggerimento

Questo problema è stato risolto in .NET Framework 4.7. Per evitare l'eccezione, eseguire l'aggiornamento a una versione di .NET Framework a partire da .NET Framework 4.7.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6.1       |
| Type    | Ridestinazione |
