---
title: Lo spazio dei nomi o il tipo specificato nelle importazioni '<qualifiedelementname>' non contiene alcun membro pubblico o non è definito
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8675d9c3b202200c89e12e7a5f51a19d9e3e0e64
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409465"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Lo spazio dei nomi o il tipo specificato nelle importazioni '\<qualifiedelementname>' non contiene alcun membro pubblico o non è definito

Lo spazio dei nomi o il tipo specificato nelle importazioni ' \<qualifiedelementname> ' non contiene alcun membro pubblico o non è stato trovato. Verificare che lo spazio dei nomi o il tipo sia definito e contenga almeno un membro pubblico. Verificare che il nome dell'alias non contenga altri alias.

Un' `Imports` istruzione specifica un elemento contenitore che non può essere trovato o non definisce `Public` membri.

Un *elemento contenitore* può essere uno spazio dei nomi, una classe, una struttura, un modulo, un'interfaccia o un'enumerazione. L'elemento contenitore contiene membri, ad esempio variabili, procedure o altri elementi contenenti.

Lo scopo dell'importazione è consentire al codice di accedere ai membri dello spazio dei nomi o ai tipi senza doverli qualificare. Il progetto potrebbe anche dover aggiungere un riferimento allo spazio dei nomi o al tipo. Per ulteriori informazioni, vedere "importazione di elementi contenitore" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Se il compilatore non riesce a trovare l'elemento contenitore specificato, non può risolvere i riferimenti che lo usano. Se trova l'elemento, ma l'elemento non espone `Public` membri, nessun riferimento può avere esito positivo. In entrambi i casi non è significativo importare l'elemento.

Tenere presente che se si importa un elemento contenitore e si assegna un alias di importazione, non è possibile usare tale alias di importazione per importare un altro elemento. Il codice seguente genera un errore del compilatore.

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

**ID errore:** BC40056

## <a name="to-correct-this-error"></a>Per correggere l'errore

1. Verificare che l'elemento contenitore sia accessibile dal progetto.

2. Verificare che la specifica dell'elemento contenitore non includa alcun alias di importazione da un'altra importazione.

3. Verificare che l'elemento contenitore esponga almeno un `Public` membro.

## <a name="see-also"></a>Vedere anche

- [Istruzione Imports (tipo e spazio dei nomi .NET)](../statements/imports-statement-net-namespace-and-type.md)
- [Istruzione Namespace](../statements/namespace-statement.md)
- [Pubblica](../modifiers/public.md)
- [Spazi dei nomi in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
