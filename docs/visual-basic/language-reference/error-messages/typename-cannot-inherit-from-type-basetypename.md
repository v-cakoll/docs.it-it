---
title: "&#39; &lt;typename&gt;&#39; non può ereditare da &lt;tipo&gt; &#39;&lt; nomeTipoBase&gt;&#39; perché espande l'accesso di base &lt;tipo&gt; all'esterno dell'assembly"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39; &lt;typename&gt;&#39; non può ereditare da &lt;tipo&gt; &#39;&lt; nomeTipoBase&gt;&#39; perché espande l'accesso di base &lt;tipo&gt; all'esterno dell'assembly
Una classe o interfaccia eredita da una classe di base o interfaccia ma con un livello di accesso meno restrittivo.  
  
 Ad esempio, un `Public` interfaccia eredita da un `Friend` , interfaccia o un `Protected` classe eredita da un `Private` classe. Espone la classe di base o l'interfaccia per accedere a oltre il livello desiderato.  
  
 **ID errore:** BC30910  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare il livello di accesso della classe derivata o dell'interfaccia sia restrittiva almeno quanto quella della classe base o interfaccia.  
  
     -oppure-  
  
-   Se è necessario il livello di accesso meno restrittivo, rimuovere il `Inherits` istruzione. È possibile ereditare da una classe di base più limitata o un'interfaccia.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
