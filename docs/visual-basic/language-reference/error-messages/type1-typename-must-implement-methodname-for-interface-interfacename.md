---
title: "&lt;type1&gt;&#39;&lt; TypeName&gt;&#39; deve implementare &#39;&lt; NomeMetodo&gt;&#39; per l'interfaccia &#39;&lt; InterfaceName&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt; TypeName&gt;&#39; deve implementare &#39;&lt; NomeMetodo&gt;&#39; per l'interfaccia &#39;&lt; InterfaceName&gt;&#39;
Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiarare una routine con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.  
  
2.  Aggiungere un `Implements` clausola alla fine del `Function` o `Sub` istruzione. Ad esempio:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
