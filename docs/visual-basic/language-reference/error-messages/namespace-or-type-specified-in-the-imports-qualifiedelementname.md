---
title: "Namespace o il tipo specificato nelle importazioni &#39; &lt;nomelementoqualificato&gt;&#39; &#39; t contiene membri pubblici o non è stato trovato"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords: BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace o il tipo specificato nelle importazioni &#39; &lt;nomelementoqualificato&gt;&#39; &#39; t contiene membri pubblici o non è stato trovato
Namespace o il tipo specificato nelle importazioni\<nomelementoqualificato >' non contiene alcun membro pubblico o non è stato trovato. Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Assicurarsi che il nome di alias non contenga altri alias.  
  
 Un `Imports` istruzione specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.  
  
 Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione. Contiene membri, ad esempio variabili, procedure o altri elementi che lo contiene.  
  
 Lo scopo di importazione è di consentire al codice per accedere ai membri di tipo o spazio dei nomi senza dover fornire il nome completo. Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o spazio dei nomi. Per ulteriori informazioni, vedere "Importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo utilizzano. Se viene trovato l'elemento, ma l'elemento non espone alcun `Public` membri, quindi alcun riferimento può avere esito positivo. In entrambi i casi è significativo per importare l'elemento.  
  
 Tenere presente che se si importa un elemento contenitore e assegna un alias di importazione, non è possibile utilizzare tale alias di importazione per importare un altro elemento. Il codice seguente genera un errore del compilatore.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **ID errore:** BC40056  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che l'elemento contenitore sia accessibile dal progetto.  
  
2.  Verificare che la specifica dell'elemento contenitore non includa alias di importazione dall'importazione di un altro.  
  
3.  Verificare che l'elemento contenitore esponga almeno `Public` membro.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
