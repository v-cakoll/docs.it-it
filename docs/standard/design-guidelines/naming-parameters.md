---
title: Denominazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 0e5b33839372e303b96bd6b84949f9a82da2f689
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646620"
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
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)
