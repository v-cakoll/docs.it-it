---
title: Procedure per la risoluzione dei problemi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: c74947e21de8ba26ffde01f6f28aea67346c2071
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002080"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Procedure per la risoluzione dei problemi (Visual Basic)

In questa pagina vengono elencati alcuni problemi comuni che possono verificarsi durante l'utilizzo delle procedure.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Restituzione di un tipo matrice da una routine Function

Se una procedura `Function` restituisce un tipo di dati della matrice, non è possibile utilizzare il nome `Function` per archiviare i valori negli elementi della matrice. Se si tenta di eseguire questa operazione, il compilatore lo interpreta come una chiamata a `Function`. Nell'esempio seguente vengono generati errori del compilatore:
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

L'istruzione `AllOnes(i) = 1` genera un errore del compilatore perché sembra chiamare `AllOnes` con un argomento del tipo di dati errato (un valore scalare `Integer` anziché una matrice `Integer`). L'istruzione `Return AllOnes()` genera un errore del compilatore perché sembra chiamare `AllOnes` senza argomento.  
  
 **Approccio corretto:** Per poter modificare gli elementi di una matrice che deve essere restituita, definire una matrice interna come variabile locale. Nell'esempio seguente viene compilato senza errori:

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a>Argomento non modificato dalla chiamata di routine

Se si intende consentire a una routine di modificare un elemento di programmazione sottostante un argomento nel codice chiamante, è necessario passarlo per riferimento. Tuttavia, una routine può accedere agli elementi di un argomento di tipo riferimento anche se viene passata per valore.

- **Variabile sottostante**. Per consentire alla stored procedure di sostituire il valore dell'elemento variable sottostante, la routine deve dichiarare il parametro [ByRef](../../../language-reference/modifiers/byref.md). Inoltre, il codice chiamante non deve racchiudere l'argomento tra parentesi, perché in questo caso verrebbe eseguito l'override del meccanismo di passaggio `ByRef`.

- **Elementi di tipo riferimento**. Se si dichiara un parametro [ByVal](../../../language-reference/modifiers/byval.md), la stored procedure non può modificare l'elemento della variabile sottostante. Tuttavia, se l'argomento è un tipo riferimento, la procedura può modificare i membri dell'oggetto a cui fa riferimento, anche se non è in grado di sostituire il valore della variabile. Ad esempio, se l'argomento è una variabile di matrice, la procedura non può assegnare una nuova matrice, ma può modificare uno o più dei relativi elementi. Gli elementi modificati si riflettono nella variabile di matrice sottostante nel codice chiamante.

Nell'esempio seguente vengono definite due procedure che accettano una variabile di matrice per valore e operano sui relativi elementi. La procedura `increase` ne aggiunge semplicemente una a ogni elemento. La procedura `replace` assegna una nuova matrice al parametro `a()`, quindi ne aggiunge uno a ogni elemento. Tuttavia, la riassegnazione non influisce sulla variabile di matrice sottostante nel codice chiamante perché `a()` è dichiarata `ByVal`.

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

Nell'esempio seguente vengono effettuate chiamate a `increase` e `replace`:

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
La prima chiamata `MsgBox` Visualizza "After increase (n): 11, 21, 31, 41 ". Poiché `n` è un tipo di riferimento, `increase` può modificarne i membri, anche se viene passato `ByVal`.

La seconda chiamata `MsgBox` Visualizza "dopo Replace (n): 11, 21, 31, 41 ". Poiché `n` viene passata `ByVal`, `replace` non può modificare la variabile `n` assegnando una nuova matrice. Quando `replace` crea la nuova istanza della matrice `k` e la assegna alla variabile locale `a`, perde il riferimento a `n` passato dal codice chiamante. Quando incrementa i membri di `a`, viene applicata solo la matrice locale `k`.

**Approccio corretto:** Per essere in grado di modificare un elemento variabile sottostante, passarlo per riferimento. Nell'esempio seguente viene illustrata la modifica della dichiarazione di `replace` che consente di sostituire una matrice con un'altra nel codice chiamante:

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a>Impossibile definire un overload

Se si desidera definire una versione di overload di una routine, è necessario utilizzare lo stesso nome ma una firma diversa. Se il compilatore non è in grado di distinguere la dichiarazione da un overload con la stessa firma, viene generato un errore.

La *firma* di una stored procedure è determinata dal nome della stored procedure e dall'elenco di parametri. Ogni overload deve avere lo stesso nome di tutti gli altri overload, ma deve essere diverso da tutti gli altri in almeno uno degli altri componenti della firma. Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).

Gli elementi seguenti, anche se riguardano l'elenco di parametri, non sono componenti della firma di una stored procedure:

- Parole chiave del modificatore di routine, ad esempio `Public`, `Shared` e `Static`.
- Nomi dei parametri.
- Parole chiave del modificatore di parametro, ad esempio `ByRef` e `Optional`.
- Tipo di dati del valore restituito (ad eccezione di un operatore di conversione).

Non è possibile eseguire l'overload di una routine variando solo uno o più elementi precedenti.

**Approccio corretto:** Per poter definire un overload di routine, è necessario variare la firma. Poiché è necessario utilizzare lo stesso nome, è necessario variare il numero, l'ordine o i tipi di dati dei parametri. In una routine generica, è possibile variare il numero di parametri di tipo. In un operatore di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md)), è possibile variare il tipo restituito.

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con argomenti facoltativi e ParamArray

Se si esegue l'overload di una routine con uno o più parametri [facoltativi](../../../language-reference/modifiers/optional.md) o un parametro [ParamArray](../../../language-reference/modifiers/paramarray.md) , è necessario evitare di duplicare gli *Overload impliciti*. Per informazioni, vedere [considerazioni sull'overload delle procedure](./considerations-in-overloading-procedures.md).

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a>Chiamata della versione errata di una routine di overload

Se una stored procedure ha diverse versioni di overload, è necessario avere familiarità con tutti gli elenchi di parametri e comprendere il modo in cui Visual Basic risolve le chiamate tra gli overload. In caso contrario, è possibile chiamare un overload diverso da quello previsto.

Quando è stato determinato l'overload da chiamare, prestare attenzione a osservare le regole seguenti:

- Specificare il numero corretto di argomenti e nell'ordine corretto.  
- Idealmente, gli argomenti devono avere esattamente gli stessi tipi di dati dei parametri corrispondenti. In ogni caso, il tipo di dati di ogni argomento deve essere ampliato a quello del parametro corrispondente. Questa situazione si verifica anche se l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) è impostata su `Off`. Se un overload richiede una conversione verso un tipo di caratteri più piccolo dall'elenco di argomenti, tale overload non è idoneo per la chiamata.
- Se si forniscono argomenti che richiedono un ampliamento, rendere i tipi di dati più vicini possibile ai tipi di dati dei parametri corrispondenti. Se due o più overload accettano i tipi di dati degli argomenti, il compilatore risolve la chiamata all'overload che chiama per il minor numero di ampliamento.

È possibile ridurre le probabilità di mancata corrispondenza tra tipi di dati tramite la parola chiave di conversione della [funzione CType](../../../language-reference/functions/ctype-function.md) durante la preparazione degli argomenti.

### <a name="overload-resolution-failure"></a>Errore di risoluzione dell'overload

Quando si chiama una routine di overload, il compilatore tenta di eliminare tutti gli overload tranne uno. Se ha esito positivo, risolve la chiamata a tale overload. Se Elimina tutti gli overload o se non è in grado di ridurre gli overload idonei a un singolo candidato, viene generato un errore.

Nell'esempio seguente viene illustrato il processo di risoluzione dell'overload:

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
Nella prima chiamata, il compilatore elimina il primo overload perché il tipo del primo argomento (`Short`) viene ridotto al tipo del parametro corrispondente (`Byte`). Elimina quindi il terzo overload perché ogni tipo di argomento nel secondo overload (`Short` e `Single`) viene ampliato al tipo corrispondente nel terzo overload (`Integer` e `Single`). Il secondo overload richiede un numero meno ampio, pertanto il compilatore lo utilizza per la chiamata.

Nella seconda chiamata, il compilatore non è in grado di eliminare gli overload sulla base della riduzione. Elimina il terzo overload per lo stesso motivo della prima chiamata, perché può chiamare il secondo overload con un minor numero di tipi di argomenti. Il compilatore, tuttavia, non è in grado di risolversi tra il primo e il secondo overload. Ogni ha un tipo di parametro definito che viene ampliato al tipo corrispondente nell'altro (`Byte` per `Short`, ma da `Single` a `Double`). Il compilatore genera quindi un errore di risoluzione dell'overload.

**Approccio corretto:** Per poter chiamare una routine di overload senza ambiguità, usare la [funzione CType](../../../language-reference/functions/ctype-function.md) per trovare la corrispondenza tra i tipi di dati degli argomenti e i tipi di parametro. Nell'esempio seguente viene illustrata una chiamata a `z` che forza la risoluzione sul secondo overload.

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con argomenti facoltativi e ParamArray

Se due overload di una stored procedure hanno firme identiche, ad eccezione del fatto che l'ultimo parametro è dichiarato [facoltativo](../../../language-reference/modifiers/optional.md) in uno e [ParamArray](../../../language-reference/modifiers/paramarray.md) nell'altro, il compilatore risolve una chiamata a tale procedura secondo la corrispondenza più vicina. Per altre informazioni, vedere [Overload Resolution](./overload-resolution.md).

## <a name="see-also"></a>Vedere anche

- [Routine](index.md)
- [Routine Sub](sub-procedures.md)
- [Routine Function](function-procedures.md)
- [Routine Property](property-procedures.md)
- [Routine di operatore](operator-procedures.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Overload della routine](procedure-overloading.md)
- [Considerazioni sull'overload di routine](considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](overload-resolution.md)
