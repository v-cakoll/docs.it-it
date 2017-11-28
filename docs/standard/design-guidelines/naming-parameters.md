---
title: Denominazione di parametri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b61f2b56b3b8bab67cec6db68a76916c6d7fa05a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="naming-parameters"></a>Denominazione di parametri
Oltre il motivo evidente di migliorare la leggibilità, è importante seguire le linee guida per i nomi dei parametri perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visiva forniscono Intellisense e funzionalità di esplorazione di classe.  
  
 **✓ SI** utilizzare Camel nei nomi di parametro.  
  
 **✓ SI** utilizzare nomi di parametro descrittivi.  
  
 **Provare a ✓** utilizzare nomi basati sul significato del parametro anziché il tipo del parametro.  
  
### <a name="naming-operator-overload-parameters"></a>Denominazione dei parametri di Overload di operatore  
 **✓ SI** utilizzare `left` e `right` per i nomi di parametro dell'operatore binario overload se è presente alcun significato per i parametri.  
  
 **✓ SI** utilizzare `value` per unario overload degli operatori i nomi dei parametri se è presente alcun significato per i parametri.  
  
 **Provare a ✓** nomi significativi per l'operatore di overload parametri se questo modo si aggiunge un valore significativo.  
  
 **X non** le abbreviazioni di utilizzare uno o più indici numerici per l'operatore di overload i nomi dei parametri.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
