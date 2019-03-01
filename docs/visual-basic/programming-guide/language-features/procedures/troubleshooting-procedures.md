---
title: Risoluzione dei problemi relativi alle routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: e29e4a3b216657b398407701530ad9bfe975dbf6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972001"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Risoluzione dei problemi relativi alle routine (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si lavora con le procedure.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Restituzione di un tipo di matrice da una routine Function  
 Se un `Function` routine restituisce un tipo di dati di matrice, non è possibile usare il `Function` nome in cui archiviare i valori negli elementi della matrice. Se si prova a eseguire questa operazione, il compilatore interpreta come una chiamata al `Function`. Nell'esempio seguente genera errori del compilatore.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 L'istruzione `allOnes(i) = 1` genera un errore del compilatore perché viene visualizzato per chiamare `allOnes` con un argomento di tipo di dati errato (un singleton `Integer` anziché un `Integer` matrice). L'istruzione `Return allOnes()` genera un errore del compilatore perché viene visualizzato per chiamare `allOnes` con nessun argomento.  
  
 **Approccio corretto:** Per essere in grado di modificare gli elementi della matrice che deve essere restituita, definire una matrice interna come una variabile locale. L'esempio seguente viene compilato senza errori.  
  
 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argomento non viene modificato dalla chiamata di routine  
 Se si prevede di consentire una procedura per modificare un elemento di programmazione sottostante a un argomento nel codice chiamante, è necessario passarlo per riferimento. Ma una procedura può accedere agli elementi di un argomento di tipo riferimento anche se viene passato per valore.  
  
-   **Variabile sottostante**. Per consentire la procedura sostituire il valore dell'elemento variabile sottostante stesso, la procedura è necessario dichiarare il parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Inoltre, il codice chiamante non deve racchiudere l'argomento racchiuso tra parentesi, perché che sostituirebbe il `ByRef` meccanismo di trasferimento.  
  
-   **Fare riferimento agli elementi di tipo**. Se si dichiara un parametro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), la procedura non è possibile modificare l'elemento variabile sottostante. Tuttavia, se l'argomento è un tipo riferimento, la procedura può modificare i membri dell'oggetto a cui fa riferimento, anche se Impossibile sostituire il valore della variabile. Ad esempio, se l'argomento è una variabile di matrice, la procedura non è possibile assegnare una nuova matrice a esso, ma è possibile modificare uno o più dei relativi elementi. Gli elementi modificati vengono riflesse nella variabile di matrice sottostante nel codice chiamante.  
  
 L'esempio seguente definisce due procedure che accettano una variabile di matrice per valore e operano sui relativi elementi. Procedure `increase` aggiunge semplicemente uno per ogni elemento. Routine `replace` assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento. Tuttavia, la riassegnazione non influiscono sulla variabile di matrice sottostante nel codice chiamante perché `a()` viene dichiarato `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 Nell'esempio seguente effettua chiamate a `increase` e `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Il primo `MsgBox` chiamata viene visualizzato "dopo aver Increase (n): 11, 21, 31, 41". In quanto `n` è un tipo di riferimento `increase` possono modificare i relativi membri, anche se viene passato `ByVal`.  
  
 Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 11, 21, 31, 41". In quanto `n` viene passato `ByVal`, `replace` non è possibile modificare la variabile `n` assegnandole una nuova matrice. Quando `replace` crea la nuova istanza della matrice `k` e la assegna alla variabile locale `a`, perde il riferimento a `n` passato dal codice chiamante. Quando incrementa i membri del `a`, solo la matrice locale `k` è interessato.  
  
 **Approccio corretto:** Per essere in grado di modificare un elemento variabile sottostante, è necessario passarlo per riferimento. Nell'esempio seguente mostra la modifica nella dichiarazione di `replace` che consente di sostituire una matrice con un oggetto nel codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]  
  
## <a name="unable-to-define-an-overload"></a>Non è possibile definire un Overload  
 Se si desidera definire una versione di overload di una stored procedure, è necessario usare lo stesso nome e una firma diversa. Se il compilatore non può distinguere la dichiarazione di un overload con la stessa firma, viene generato un errore.  
  
 Il *firma* di una stored procedure viene determinato tramite il nome della routine e l'elenco di parametri. Ogni overload deve avere lo stesso nome di tutti gli altri overload, ma deve essere diverso da tutti gli elementi in almeno uno degli altri componenti della firma. Per altre informazioni, vedere [Procedure Overloading](./procedure-overloading.md).  
  
 Gli elementi seguenti, anche se si riferiscono all'elenco di parametri, non sono componenti della firma di una routine:  
  
-   Parole chiave di modificatore di routine, ad esempio `Public`, `Shared`, e `Static`  
  
-   Nomi dei parametri  
  
-   Parole chiave di modificatori di parametro, ad esempio `ByRef` e `Optional`  
  
-   il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)  
  
 È possibile eseguire l'overload di una procedura variando solo uno o più degli elementi precedenti.  
  
 **Approccio corretto:** Per poter definire un overload di routine, è necessario modificare la firma. Perché è necessario utilizzare lo stesso nome, è necessario modificare il numero, ordine o tipi di dati dei parametri. In una routine generica, è possibile variare il numero di parametri di tipo. In un operatore di conversione ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)), è possibile variare il tipo restituito.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con facoltativa e argomenti ParamArray  
 Se si esegue l'overload di una procedura con una o più [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) i parametri o una [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, è necessario evitare la duplicazione del *overload impliciti*. Per informazioni, vedere [considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>La chiamata a una versione errata di una routine di overload  
 Se una procedura dispone di diverse versioni di overload, è necessario avere familiarità con tutti i relativi elenchi di parametri e comprendere come Visual Basic consente di risolvere le chiamate tra gli overload. In caso contrario, è possibile chiamare un overload diverso da quello previsto.  
  
 Dopo aver stabilito quale eseguire l'overload che si desidera chiamare, prestare attenzione a osservare le regole seguenti:  
  
-   Specificare il numero corretto di argomenti e nell'ordine corretto.  
  
-   In teoria, gli argomenti devono avere esattamente gli stessi tipi di dati dei parametri corrispondenti. In ogni caso, il tipo di dati di ogni argomento deve ampliarsi a quello del parametro corrispondente. Questo vale anche con il [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) impostato su `Off`. Se un overload richiede qualsiasi conversione di narrowing dall'elenco di argomenti, che eseguono l'overload non è idoneo a essere chiamato.  
  
-   Se si forniscono argomenti che richiedono un ampliamento, rendere i relativi tipi di dati più vicino possibile ai tipi di dati di parametro corrispondente. Se due o più overload accettano i tipi di dati di argomento, il compilatore risolve la chiamata all'overload che richiede la quantità minima di ampliamento.  
  
 È possibile ridurre il rischio di mancate corrispondenze tra tipi di dati usando il [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) parola chiave di conversione durante la preparazione degli argomenti.  
  
### <a name="overload-resolution-failure"></a>Errore di risoluzione dell'overload  
 Quando si chiama una routine di overload, il compilatore prova a eliminare tutto tranne uno degli overload. Caso di esito positivo, la chiamata a tale overload viene risolta. Se vengono eliminati tutti gli overload o se non è possibile ridurre gli overload idonei a uno solo, viene generato un errore.  
  
 L'esempio seguente illustra il processo di risoluzione dell'overload.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload, perché il tipo del primo argomento (`Short`) viene convertito nel tipo del parametro corrispondente (`Byte`). Il terzo overload viene quindi eliminato poiché ogni tipo di argomento nel secondo overload (`Short` e `Single`) viene ampliato al tipo del terzo overload corrispondente (`Integer` e `Single`). Il secondo overload richiede un ampliamento minore, in modo che il compilatore lo usa per la chiamata.  
  
 Nella seconda chiamata, il compilatore non è possibile eliminare uno degli overload sulla base di restrizione. Elimina il terzo overload per lo stesso motivo della prima chiamata, perché può chiamare il secondo overload con meno di ampliamento dei tipi di argomento. Tuttavia, il compilatore non può risolvere tra i primi e il secondo overload. Ognuno ha un tipo di parametro definito che viene ampliato al tipo corrispondente in altro (`Byte` al `Short`, ma `Single` a `Double`). Di conseguenza, il compilatore genera un errore di risoluzione dell'overload.  
  
 **Approccio corretto:** Per essere in grado di chiamare una routine di overload senza ambiguità, usare [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) in modo che corrispondano ai tipi di dati di argomenti per i tipi di parametro. Nell'esempio seguente viene illustrata una chiamata a `z` che forza la risoluzione per il secondo overload.  
  
 [!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con facoltativa e argomenti ParamArray  
 Se due overload di una stored procedure hanno firme identiche ad eccezione del fatto che l'ultimo parametro viene dichiarato [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in altro, il compilatore risolve una chiamata a tale procedura in base alla corrispondenza più vicina. Per altre informazioni, vedere [Overload Resolution](./overload-resolution.md).  
  
## <a name="see-also"></a>Vedere anche
- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Overload della routine](./procedure-overloading.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)
