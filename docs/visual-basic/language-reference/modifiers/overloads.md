---
title: Overloads
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 44823b409cfa81dc889aabacf101fac90bf851e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351414"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)

Specifica che una proprietà o una routine ridichiara una o più proprietà o routine esistenti con lo stesso nome.

## <a name="remarks"></a>Note

*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope. Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.

## <a name="rules"></a>Regole

- **Declaration Context.** You can use `Overloads` only in a property or procedure declaration statement.

- **Combined Modifiers.** You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.

- **Required Differences.** The *signature* in this declaration must be different from the signature of every property or procedure that it overloads. La firma comprende il nome della proprietà o della routine e gli elementi seguenti:

  - numero dei parametri

  - ordine dei parametri

  - tipi di dati dei parametri

  - numero dei parametri di tipo (per una routine generica)

  - tipo restituito (solo per una routine di operatore di conversione)

  Tutti gli overload devono avere lo stesso nome, ma ognuno deve essere diverso da tutti gli altri per uno o più elementi tra quelli elencati in precedenza. Questo consente al compilatore di distinguere la versione da usare quando il codice chiama la proprietà o la routine.

- **Disallowed Differences.** Poiché gli elementi riportati di seguito non fanno parte della firma, la relativa modifica non è valida per l'overload di una proprietà o di una routine:

  - la capacità di restituire un valore (per una routine)

  - il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)

  - i nomi dei parametri o dei parametri di tipo

  - i vincoli definiti sui parametri di tipo (per una routine generica)

  - le parole chiave di modificatori di parametro (ad esempio `ByRef` o `Optional`)

  - e parole chiave di modificatori di proprietà o di routine (ad esempio `Public` o `Shared`)

- **Optional Modifier.** You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class. Se tuttavia si usa `Overloads` in una dichiarazione, è necessario usarlo in tutte.

- **Shadowing and Overloading.** `Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class. Quando si usa `Overloads` a questo scopo, è necessario dichiarare la proprietà o il metodo con lo stesso nome e lo stesso elenco di parametri del membro della classe base, senza specificare la parola chiave `Shadows`.

Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.

Il modificatore `Overloads` può essere usato nei contesti seguenti:

- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)

- [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)

- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)

- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overload della routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
