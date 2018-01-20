---
title: "Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a17877b2335ee010a97f0b522bd4c399867cd7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
Un'operazione ciclica non è riuscita. Queste operazioni sono cicliche e quindi non possono essere completate. Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Nozioni fondamentali di debug: i punti di interruzione](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
