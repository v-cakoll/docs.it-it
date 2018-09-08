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
ms.openlocfilehash: 8e6a8a1dcdcb8fa3311b040c72987f0f76e681fc
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086472"
---
# <a name="naming-parameters"></a>Denominazione di parametri
Oltre a motivazione ovvia di migliorare la leggibilità, è importante seguire le linee guida per i nomi dei parametri perché i parametri vengono visualizzati nella documentazione e nella finestra di progettazione quando gli strumenti di progettazione visiva forniscono a Intellisense e funzionalità di esplorazione di classe.  
  
 **✓ DO** utilizzare Camel nei nomi di parametro.  
  
 **✓ DO** utilizzare nomi di parametro descrittivo.  
  
 **✓ CONSIDER** utilizzare nomi basati sul significato del parametro anziché il tipo del parametro.  
  
### <a name="naming-operator-overload-parameters"></a>Denominazione di parametri di Overload di operatore  
 **✓ DO** usare `left` e `right` per i nomi di parametro dell'operatore binario overload se è presente alcun significato per i parametri.  
  
 **✓ DO** utilizzare `value` per unario overload degli operatori i nomi dei parametri se è presente alcun significato per i parametri.  
  
 **✓ CONSIDER** nomi significativi per l'operatore di overload parametri se questo modo si aggiunge un valore significativo.  
  
 **X DO NOT** le abbreviazioni di utilizzare uno o più indici numerici per l'operatore di overload i nomi dei parametri.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
