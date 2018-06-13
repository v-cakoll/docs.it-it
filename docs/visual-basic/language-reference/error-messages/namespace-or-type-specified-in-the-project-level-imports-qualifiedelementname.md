---
title: Namespace o il tipo specificato nelle importazioni a livello di progetto &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stato trovato
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595813"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace o il tipo specificato nelle importazioni a livello di progetto &#39; &lt;nomeelementoqualificato&gt; &#39; &#39;t contiene membri pubblici o non è stato trovato
Namespace o il tipo specificato nelle importazioni a livello di progetto\<nomelementoqualificato >' non contiene alcun membro pubblico o non è stato trovato. Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Assicurarsi che il nome di alias non contenga altri alias.  
  
 Una proprietà di importazione di un progetto specifica un elemento contenitore che può essere trovato o non definisce alcun `Public` membri.  
  
 Oggetto *contenente l'elemento* può essere un spazio dei nomi, classe, struttura, modulo, interfaccia o enumerazione. Contiene membri, ad esempio variabili, procedure o altri elementi che lo contiene.  
  
 Lo scopo di importazione è di consentire al codice per accedere ai membri di tipo o spazio dei nomi senza dover fornire il nome completo. Il progetto potrebbe essere necessario anche aggiungere un riferimento al tipo o spazio dei nomi. Per ulteriori informazioni, vedere "Importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Se il compilatore non trova l'elemento contenitore specificato, non sarà possibile risolvere i riferimenti che lo utilizzano. Se viene trovato l'elemento, ma l'elemento non espone alcun `Public` membri, quindi alcun riferimento può avere esito positivo. In entrambi i casi è significativo per importare l'elemento.  
  
 Utilizzare il **progettazione** per specificare gli elementi da importare. Utilizzare il **spazi dei nomi importati** sezione la **riferimenti** pagina. È possibile ottenere il **Progettazione progetti** facendo doppio clic su di **progetto** icona in **Esplora**.  
  
 **ID errore:** BC40057  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Aprire il **Progettazione progetti** e passare il **riferimento** pagina.  
  
2.  Nel **spazi dei nomi importati** sezione, verificare che l'elemento contenitore sia accessibile dal progetto.  
  
3.  Verificare che l'elemento contenitore esponga almeno `Public` membro.  
  
## <a name="see-also"></a>Vedere anche  
 [Pagina Riferimenti, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
