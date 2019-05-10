---
title: Overloads (Visual Basic)
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
ms.openlocfilehash: ab8660ff0cf02956e760132f5aad69e359913950
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661090"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)
Specifica che una proprietà o una routine ridichiara una o più proprietà o routine esistenti con lo stesso nome.  
  
## <a name="remarks"></a>Note  
 *L'overload* è la pratica di fornire più di una definizione per un determinato nome di proprietà o routine nello stesso ambito. La ridichiarazione di una proprietà o routine con una firma diversa viene talvolta chiamata *nascondere con la firma*.  
  
## <a name="rules"></a>Regole  
  
- **Contesto della dichiarazione.** È possibile usare `Overloads` solo in un'istruzione per la dichiarazione di proprietà o routine.  
  
- **Modificatori combinati.** Non è possibile specificare `Overloads` assieme [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) nella stessa dichiarazione di routine.  
  
- **Differenze necessarie.** Il *firma* in questa dichiarazione deve essere diverso dalla firma di tutte le proprietà o routine che esegue l'overload. La firma comprende il nome della proprietà o della routine e gli elementi seguenti:  
  
    - numero dei parametri  
  
    - ordine dei parametri  
  
    - tipi di dati dei parametri  
  
    - numero dei parametri di tipo (per una routine generica)  
  
    - tipo restituito (solo per una routine di operatore di conversione)  
  
     Tutti gli overload devono avere lo stesso nome, ma ognuno deve essere diverso da tutti gli altri per uno o più elementi tra quelli elencati in precedenza. Questo consente al compilatore di distinguere la versione da usare quando il codice chiama la proprietà o la routine.  
  
- **Differenze non consentite.** Poiché gli elementi riportati di seguito non fanno parte della firma, la relativa modifica non è valida per l'overload di una proprietà o di una routine:  
  
    - la capacità di restituire un valore (per una routine)  
  
    - il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)  
  
    - i nomi dei parametri o dei parametri di tipo  
  
    - i vincoli definiti sui parametri di tipo (per una routine generica)  
  
    - le parole chiave di modificatori di parametro (ad esempio `ByRef` o `Optional`)  
  
    - e parole chiave di modificatori di proprietà o di routine (ad esempio `Public` o `Shared`)  
  
- **Modificatore facoltativo.** Non è necessario usare il modificatore `Overloads` quando si definiscono più proprietà o routine in overload nella medesima classe. Se tuttavia si usa `Overloads` in una dichiarazione, è necessario usarlo in tutte.  
  
- **Shadowing e overload.** `Overloads` è anche utilizzabile per nascondere un membro esistente o un set di membri in overload, in una classe base. Quando si usa `Overloads` a questo scopo, è necessario dichiarare la proprietà o il metodo con lo stesso nome e lo stesso elenco di parametri del membro della classe base, senza specificare la parola chiave `Shadows`.  
  
 Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.  
  
 Il modificatore `Overloads` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overload della routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
