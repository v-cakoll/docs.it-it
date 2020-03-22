---
title: Me, My, MyBase e MyClass
ms.date: 07/20/2015
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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400848"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase e MyClass in Visual Basic
`Me`, `My` `MyBase`, `MyClass` e in Visual Basic hanno nomi simili, ma scopi diversi. In questo argomento viene descritta ognuna di queste entità per distinguerle.  
  
## <a name="me"></a>Me stesso  
 La `Me` parola chiave fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui il codice è attualmente in esecuzione. `Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente. L'utilizzo `Me` è particolarmente utile per passare informazioni sull'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o modulo.  
  
 Si supponga, ad esempio, di disporre della procedura seguente in un modulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 È possibile chiamare questa routine e <xref:System.Windows.Forms.Form> passare l'istanza corrente della classe come argomento utilizzando l'istruzione seguente.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 La `My` funzionalità consente di accedere in modo semplice e intuitivo a numerose classi .NET Framework, consentendo all'utente di Visual Basic di interagire con il computer, l'applicazione, le impostazioni, le risorse e così via.  
  
## <a name="mybase"></a>MyBase  
 La `MyBase` parola chiave si comporta come una variabile oggetto che fa riferimento alla classe base dell'istanza corrente di una classe. `MyBase`viene in genere utilizzato per accedere ai membri della classe base sottoposti a override o sottoposti a shadowing in una classe derivata. `MyBase.New`viene utilizzato per chiamare in modo esplicito un costruttore di classi base da un costruttore di classi derivate.  
  
## <a name="myclass"></a>MyClass  
 La `MyClass` parola chiave si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come originariamente implementata. `MyClass`è simile `Me`a , ma tutte le chiamate al `NotOverridable`metodo su di esso vengono considerate come se il metodo fosse .  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
