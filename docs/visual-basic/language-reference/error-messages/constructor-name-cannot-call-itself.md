---
title: "Costruttore &#39; &lt;nome&gt;&#39; non può chiamare se stesso"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Costruttore &#39; &lt;nome&gt;&#39; non può chiamare se stesso
Oggetto `Sub New` routine in una classe o struttura chiama se stessa.  
  
 Lo scopo di un costruttore è inizializzare un'istanza di una classe o struttura quando viene inizialmente creato. Una classe o struttura può contenere più costruttori, purché dispongano di elenchi di parametri diversi. Un costruttore è autorizzato a chiamare un altro costruttore per eseguire le funzionalità oltre a proprio. Ma non ha significato per un costruttore da chiamare se stesso e in realtà il risultato sarà una ricorsione infinita se è consentito.  
  
 **ID errore:** BC30298  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare l'elenco di parametri del costruttore da chiamare. Deve essere diversa da quella del costruttore della chiamata.  
  
2.  Se non si intende chiamare un costruttore diverso, rimuovere il `Sub New` chiamare completamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Durata degli oggetti: come creare e distruggere oggetti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
