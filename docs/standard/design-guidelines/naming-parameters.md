---
title: Denominazione di parametri
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6b96bb05c52de4bfd8b6ad6b972c9d22ca66da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="naming-parameters"></a>Denominazione di parametri
Oltre il motivo evidente di migliorare la leggibilità, è importante seguire le linee guida per i nomi dei parametri perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visiva forniscono Intellisense e funzionalità di esplorazione di classe.  
  
 **✓ SI** utilizzare Camel nei nomi di parametro.  
  
 **✓ SI** utilizzare nomi di parametro descrittivo.  
  
 **✓ Provare a** utilizzare nomi basati sul significato del parametro anziché il tipo del parametro.  
  
### <a name="naming-operator-overload-parameters"></a>Denominazione dei parametri di Overload di operatore  
 **✓ SI** usare `left` e `right` per i nomi di parametro dell'operatore binario overload se è presente alcun significato per i parametri.  
  
 **✓ SI** utilizzare `value` per unario overload degli operatori i nomi dei parametri se è presente alcun significato per i parametri.  
  
 **✓ Provare a** nomi significativi per l'operatore di overload parametri se questo modo si aggiunge un valore significativo.  
  
 **X non** le abbreviazioni di utilizzare uno o più indici numerici per l'operatore di overload i nomi dei parametri.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
