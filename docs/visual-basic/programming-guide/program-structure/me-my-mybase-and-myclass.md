---
title: Me, My, MyBase e MyClass in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bebf404cd65d1b3a2c4059d3a7c986f0157dfe2d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase e MyClass in Visual Basic
`Me`, `My`, `MyBase`, e `MyClass` in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] con nomi simili, ma scopi diversi. Questo argomento descrive ognuna di queste entità per distinguerli.  
  
## <a name="me"></a>Me  
 Il `Me` (parola chiave) fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice. `Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente. Utilizzando `Me` è particolarmente utile per passare le informazioni sull'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o modulo.  
  
 Ad esempio, si supponga la procedura seguente in un modulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 È possibile chiamare la routine e passare l'istanza corrente del <xref:System.Windows.Forms.Form> classe come un argomento tramite l'istruzione seguente.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Il `My` fornisce un accesso semplice e intuitivo per un numero di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classi, l'abilitazione di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per interagire con il computer, applicazioni, impostazioni, risorse e così via.  
  
## <a name="mybase"></a>MyBase  
 Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase`viene comunemente utilizzato per accedere ai membri di classe di base che vengono sottoposti a override o shadowing in una classe derivata. `MyBase.New`viene utilizzato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.  
  
## <a name="myclass"></a>MyClass  
 Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass`è simile a `Me`, ma tutte le chiamate al metodo su di essa vengono considerate come se fosse il metodo `NotOverridable`.  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
