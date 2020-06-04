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
ms.openlocfilehash: b4470e5c178c0f66dc33956ea0131d4eabc51d46
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397467"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase e MyClass in Visual Basic
`Me`, `My` , `MyBase` e `MyClass` in Visual Basic hanno nomi simili, ma scopi diversi. In questo argomento vengono descritte le singole entità per distinguerle.  
  
## <a name="me"></a>Me stesso  
 La `Me` parola chiave fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice. `Me`si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente. L'utilizzo di `Me` è particolarmente utile per passare informazioni sull'istanza attualmente in esecuzione di una classe o di una struttura a una routine in un'altra classe, struttura o modulo.  
  
 Si supponga, ad esempio, di avere la procedura seguente in un modulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 È possibile chiamare questa procedura e passare l'istanza corrente della <xref:System.Windows.Forms.Form> classe come argomento usando l'istruzione seguente.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Questa `My` funzionalità consente di accedere in modo semplice e intuitivo a numerose classi di .NET Framework, consentendo all'utente di Visual Basic di interagire con il computer, l'applicazione, le impostazioni, le risorse e così via.  
  
## <a name="mybase"></a>MyBase  
 La `MyBase` parola chiave si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase`viene in genere usato per accedere ai membri della classe di base sottoposti a override o nascosti in una classe derivata. `MyBase.New`viene usato per chiamare in modo esplicito un costruttore della classe base da un costruttore di classe derivata.  
  
## <a name="myclass"></a>MyClass  
 La `MyClass` parola chiave si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass`è simile a `Me` , ma tutte le chiamate al metodo su di essa sono trattate come se il metodo fosse `NotOverridable` .  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'ereditarietà](../language-features/objects-and-classes/inheritance-basics.md)
