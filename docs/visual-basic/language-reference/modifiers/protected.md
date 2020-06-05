---
title: Protetta
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: d66ed68004f8b6ef21ae703f02b317589814764b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398220"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)

Un modificatore di accesso ai membri che specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno della propria classe o da una classe derivata.

## <a name="remarks"></a>Commenti

A volte un elemento di programmazione dichiarato in una classe contiene dati sensibili o codice limitato e si vuole limitare l'accesso all'elemento. Tuttavia, se la classe è ereditabile e si prevede una gerarchia di classi derivate, potrebbe essere necessario che queste classi derivate accedano ai dati o al codice. In tal caso, è necessario che l'elemento sia accessibile sia dalla classe di base che da tutte le classi derivate. Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Protected` .

> [!NOTE]
> Il `Protected` modificatore di accesso può essere combinato con altri due modificatori:
>
> - Il modificatore [Friend protetto](protected-friend.md) rende accessibile un membro della classe da tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe.
> - Il modificatore [protected privato](private-protected.md) rende accessibile a un membro della classe i tipi derivati, ma solo all'interno dell'assembly che lo contiene.

## <a name="rules"></a>Regole

**Contesto della dichiarazione. ** È possibile usare `Protected` solo a livello di classe. Ciò significa che il contesto di dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** Tutto il codice in una classe può accedere ai relativi elementi. Il codice in qualsiasi classe che deriva da una classe base può accedere a tutti gli `Protected` elementi della classe di base. Questo vale per tutte le generazioni di derivazione. Ciò significa che una classe può accedere `Protected` agli elementi della classe di base della classe di base e così via.

     L'accesso protetto non è un superset o un subset di accesso Friend.

- **Modificatori di accesso.** Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Il modificatore `Protected` può essere usato nei contesti seguenti:

- [Istruzione Class](../statements/class-statement.md)

- [Istruzione Const](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Istruzione Delegate](../statements/delegate-statement.md)

- [Istruzione Dim](../statements/dim-statement.md)

- [Istruzione Enum](../statements/enum-statement.md)

- [Istruzione Event](../statements/event-statement.md)

- [Istruzione Function](../statements/function-statement.md)

- [Istruzione Interface](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Istruzione Structure](../statements/structure-statement.md)

- [Istruzione Sub](../statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Pubblica](public.md)
- [Amico](friend.md)
- [Privata](private.md)
- [Privato protetto](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
