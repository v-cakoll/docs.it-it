---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' a livello di progetto non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 105fa8da838938d13022c210c1f65cdafd251003
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918307"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Namespace o il tipo specificato nelle istruzioni 'Imports a livello di progetto\<nomeelementoqualificato >' non contiene alcun membro pubblico o non è stata trovata
Namespace o il tipo specificato nelle istruzioni 'Imports a livello di progetto\<nomeelementoqualificato >' non contiene alcun membro pubblico o non è stata trovata. Assicurarsi che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Assicurarsi che il nome di alias non contenga altri alias.  
  
 Una proprietà di importazione di un progetto specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.  
  
 Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione. L'elemento contenitore contiene membri, ad esempio variabili, routine o altri elementi che lo contiene.  
  
 Lo scopo dell'importazione è di consentire al codice per accedere ai membri dello spazio dei nomi o un tipo senza dover fornire il nome completo. Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o dello spazio dei nomi. Per altre informazioni, vedere "Importazione di elementi contenitore" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo usano. Se viene trovato l'elemento ma l'elemento non espone alcun `Public` membri, non esiste alcun riferimento può essere esito positivo. In entrambi i casi è significativo per l'elemento import.  
  
 Si utilizza il **Progettazione progetti** per specificare gli elementi da importare. Usare il **spazi dei nomi importati** sezione il **riferimenti** pagina. È possibile ottenere il **creazione progetti** facendo doppio clic sul **My Project** icona nel **Esplora soluzioni**.  
  
 **ID errore:** BC40057  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Aprire il **creazione progetti** e passare alle **riferimento** pagina.  
  
2. Nel **spazi dei nomi importati** sezione, verificare che l'elemento contenitore è accessibile dal progetto.  
  
3. Verificare che l'elemento contenitore espone ad almeno uno `Public` membro.  
  
## <a name="see-also"></a>Vedere anche

- [Pagina Riferimenti, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
