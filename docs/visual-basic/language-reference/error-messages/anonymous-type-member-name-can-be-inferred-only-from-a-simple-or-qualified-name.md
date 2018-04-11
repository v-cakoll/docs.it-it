---
title: Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7068928a17ee5fdb7bf6b5e0a40aaa7e5ef32f11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti
Non è possibile dedurre il nome di un membro di tipo anonimo da un'espressione complessa.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Per ulteriori informazioni sulle origini da cui i tipi anonimi possono dedurre i nomi dei membri e tipi, vedere [procedura: dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
 **ID errore:** BC36556  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assegnare l'espressione a un nome di membro, come illustrato nel codice seguente:  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
