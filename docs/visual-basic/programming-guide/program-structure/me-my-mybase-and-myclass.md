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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347343"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase e MyClass in Visual Basic
`Me`, `My`, `MyBase`e `MyClass` in Visual Basic hanno nomi simili, ma a scopi diversi. In questo argomento vengono descritte le singole entità per distinguerle.  
  
## <a name="me"></a>Me  
 La parola chiave `Me` fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice. `Me` si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente. L'uso di `Me` è particolarmente utile per passare informazioni sull'istanza attualmente in esecuzione di una classe o di una struttura a una routine in un'altra classe, struttura o modulo.  
  
 Si supponga, ad esempio, di avere la procedura seguente in un modulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 È possibile chiamare questa procedura e passare l'istanza corrente della classe <xref:System.Windows.Forms.Form> come argomento usando l'istruzione seguente.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 La funzionalità `My` consente di accedere in modo semplice e intuitivo a diverse classi .NET Framework, consentendo al Visual Basic utente di interagire con il computer, l'applicazione, le impostazioni, le risorse e così via.  
  
## <a name="mybase"></a>MyBase  
 La parola chiave `MyBase` si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase` viene comunemente usato per accedere ai membri della classe di base sottoposti a override o nascosti in una classe derivata. `MyBase.New` viene usato per chiamare in modo esplicito un costruttore della classe base da un costruttore di classe derivata.  
  
## <a name="myclass"></a>MyClass  
 La parola chiave `MyClass` si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass` è simile a `Me`, ma tutte le chiamate al metodo su di essa sono trattate come se il metodo venisse `NotOverridable`to.  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
