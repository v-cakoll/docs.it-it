---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' a livello di progetto non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 0ee235252d69e6f77ce53b048f45e73d0969e864
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409452"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Lo spazio dei nomi o il tipo specificato nelle importazioni '\<qualifiedelementname>' a livello di progetto non contiene alcun membro pubblico o non è definito
Lo spazio dei nomi o il tipo specificato nelle importazioni a livello di progetto ' \<qualifiedelementname> ' non contiene alcun membro pubblico o non è stato trovato. Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Verificare che il nome dell'alias non contenga altri alias.  
  
 Una proprietà import di un progetto specifica un elemento contenitore che non può essere trovato o non definisce `Public` membri.  
  
 Un *elemento contenitore* può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia o un'enumerazione. L'elemento contenitore contiene membri, ad esempio variabili, procedure o altri elementi contenenti.  
  
 Lo scopo dell'importazione è consentire al codice di accedere ai membri dello spazio dei nomi o ai tipi senza doverli qualificare. Il progetto potrebbe anche dover aggiungere un riferimento allo spazio dei nomi o al tipo. Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Se il compilatore non riesce a trovare l'elemento contenitore specificato, non può risolvere i riferimenti che lo usano. Se trova l'elemento, ma l'elemento non espone `Public` membri, nessun riferimento può avere esito positivo. In entrambi i casi non è significativo importare l'elemento.  
  
 Per specificare gli elementi da importare, è possibile utilizzare **Progettazione progetti** . Utilizzare la sezione **spazi dei nomi importati** della pagina **riferimenti** . È possibile ottenere la creazione di **progetti** facendo doppio clic sull'icona del **progetto** in **Esplora soluzioni**.  
  
 **ID errore:** BC40057  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Aprire **Progettazione progetti** e passare alla pagina di **riferimento** .  
  
2. Nella sezione **spazi dei nomi importati** verificare che l'elemento contenitore sia accessibile dal progetto.  
  
3. Verificare che l'elemento contenitore esponga almeno un `Public` membro.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti (pagina), Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Pubblica](../modifiers/public.md)
- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
