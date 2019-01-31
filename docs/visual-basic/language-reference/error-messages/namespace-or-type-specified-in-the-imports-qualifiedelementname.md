---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: d19a769b33b3b63b7f431b73841f49632e41f9e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288275"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Namespace o il tipo specificato nelle istruzioni 'Imports\<nomeelementoqualificato >' non contiene alcun membro pubblico o non è stata trovata
Namespace o il tipo specificato nelle istruzioni 'Imports\<nomeelementoqualificato >' non contiene alcun membro pubblico o non è stata trovata. Assicurarsi che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Assicurarsi che il nome di alias non contenga altri alias.  
  
 Un' `Imports` istruzione specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.  
  
 Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione. L'elemento contenitore contiene membri, ad esempio variabili, routine o altri elementi che lo contiene.  
  
 Lo scopo dell'importazione è di consentire al codice per accedere ai membri dello spazio dei nomi o un tipo senza dover fornire il nome completo. Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o dello spazio dei nomi. Per altre informazioni, vedere "Importazione di elementi contenitore" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo usano. Se viene trovato l'elemento ma l'elemento non espone alcun `Public` membri, non esiste alcun riferimento può essere esito positivo. In entrambi i casi è significativo per l'elemento import.  
  
 Tenere presente che se si importa un elemento che lo contiene e assegnarvi un alias di importazione, quindi è possibile usare tale alias di importazione per importare un altro elemento. Il codice seguente genera un errore del compilatore.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **ID errore:** BC40056  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che l'elemento contenitore è accessibile dal progetto.  
  
2.  Verificare che la specifica dell'elemento contenitore non è inclusa qualsiasi alias di importazione da un'altra importazione.  
  
3.  Verificare che l'elemento contenitore espone ad almeno uno `Public` membro.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
