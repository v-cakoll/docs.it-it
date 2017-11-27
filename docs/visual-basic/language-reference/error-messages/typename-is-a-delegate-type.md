---
title: "&#39; &lt;typename&gt;&#39; è un tipo delegato"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords: BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39; &lt;typename&gt;&#39; è un tipo delegato
'\<nomeTipo >' è un tipo delegato. Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti. Spesso è possibile utilizzare un'espressione AddressOf anziché una costruzione di delegati.  
  
 Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.  
  
 È possibile fornire una sola `AddressOf` espressione durante la creazione di una nuova istanza di delegato.  
  
 Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passano più argomenti, o se si passa un singolo argomento che non è un valido `AddressOf` espressione.  
  
 **ID errore:** BC32008  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Usare un singolo `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Procedura: Richiamare un metodo delegato](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
