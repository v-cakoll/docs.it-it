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
ms.openlocfilehash: f66e7f7444f2d3b1bb58bae6008f8896c81c2f76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655519"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Risoluzione dei problemi relativi alle routine (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi durante l'utilizzo delle procedure.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Restituzione di un tipo di matrice da una routine Function  
 Se un `Function` routine restituisce un tipo di dati della matrice, non è possibile utilizzare il `Function` nome con cui archiviare i valori degli elementi della matrice. Se si tenta di eseguire questa operazione, il compilatore lo interpreta come una chiamata al `Function`. L'esempio seguente genera errori del compilatore.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 L'istruzione `allOnes(i) = 1` genera un errore del compilatore perché sembra chiamare `allOnes` con un argomento di tipo di dati errato (un singleton `Integer` anziché un `Integer` matrice). L'istruzione `Return allOnes()` genera un errore del compilatore perché sembra chiamare `allOnes` senza alcun argomento.  
  
 **Approccio corretto:** per essere in grado di modificare gli elementi di una matrice che deve essere restituita, definire una matrice interna come una variabile locale. Nell'esempio seguente viene compilata senza errori.  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argomento non viene modificato dalla chiamata di routine  
 Se si intende consentire una stored procedure per modificare un elemento di programmazione sottostante a un argomento nel codice chiamante, è necessario passare per riferimento. Tuttavia, una stored procedure può accedere agli elementi di un argomento di tipo riferimento anche se viene passato per valore.  
  
-   **Variabile sottostante**. Per consentire la procedura per sostituire il valore dell'elemento variabile sottostante, la procedura è necessario dichiarare il parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Inoltre, il codice chiamante non deve racchiudere l'argomento tra parentesi, perché che eseguirà l'override di `ByRef` meccanismo di passaggio.  
  
-   **Fare riferimento a elementi di tipo**. Se si dichiara un parametro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), la routine non è possibile modificare l'elemento variabile sottostante. Tuttavia, se l'argomento è un tipo riferimento, la procedura può modificare i membri dell'oggetto a cui fa riferimento, anche se Impossibile sostituire il valore della variabile. Ad esempio, se l'argomento è una variabile di matrice, la procedura non è possibile assegnare una nuova matrice a esso, ma è possibile modificare uno o più dei relativi elementi. Gli elementi modificati vengono riflesse nella variabile di matrice sottostante nel codice chiamante.  
  
 L'esempio seguente definisce due procedure che accettano una variabile di matrice per valore e operano sui relativi elementi. Procedura `increase` aggiunge semplicemente uno per ogni elemento. Procedura `replace` assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento. Tuttavia, la riassegnazione non influiscono sulla variabile di matrice sottostante nel codice chiamante perché `a()` è dichiarato `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 Nell'esempio seguente effettua chiamate a `increase` e `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41". Poiché `n` è un tipo riferimento, `increase` possibile modificare i relativi membri, anche se viene passato `ByVal`.  
  
 Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 11, 21, 31, 41". Poiché `n` viene passato `ByVal`, `replace` non è possibile modificare la variabile `n` assegnando una nuova matrice. Quando `replace` crea una nuova istanza di matrice `k` e assegnarlo alla variabile locale `a`, perde il riferimento a `n` passato al codice chiamante. Quando incrementa i membri di `a`, solo la matrice locale `k` è interessato.  
  
 **Approccio corretto:** per essere in grado di modificare un elemento variabile sottostante, passarlo come riferimento. Nell'esempio seguente mostra la modifica nella dichiarazione di `replace` che consente di sostituire una matrice con un altro nel codice chiamante.  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>Non è possibile definire un Overload  
 Se si desidera definire una versione di overload di una stored procedure, è necessario utilizzare lo stesso nome e una firma diversa. Se il compilatore non è possibile distinguere la dichiarazione da un overload con la stessa firma, viene generato un errore.  
  
 Il *firma* di una stored procedure è determinato dal nome della stored procedure e l'elenco di parametri. Ogni overload deve avere lo stesso nome di tutti gli altri overload, ma deve essere diverso da tutti gli elementi in almeno uno degli altri componenti della firma. Per ulteriori informazioni, vedere [overload di routine](./procedure-overloading.md).  
  
 I seguenti elementi, anche se si riferiscono all'elenco di parametri, non sono componenti di firma di una routine:  
  
-   Parole chiave di modificatore di routine, ad esempio `Public`, `Shared`, e `Static`  
  
-   Nomi dei parametri  
  
-   Parole chiave di modificatori di parametro, ad esempio `ByRef` e `Optional`  
  
-   Il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)  
  
 È possibile eseguire l'overload di una routine modificando solo uno o più degli elementi precedenti.  
  
 **Approccio corretto:** per essere in grado di definire un overload di routine, è necessario modificare la firma. Perché è necessario utilizzare lo stesso nome, è necessario modificare il numero, ordine o tipi di dati dei parametri. In una routine generica, è possibile variare il numero di parametri di tipo. In un operatore di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)), è possibile variare il tipo restituito.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con facoltativo e argomenti ParamArray  
 Se si esegue l'overload di una routine con una o più [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) parametri o un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parametro, è necessario evitare la duplicazione del *overload impliciti*. Per informazioni, vedere [considerazioni sull'overload procedure](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>La chiamata a una versione errata di una routine di overload  
 Se una stored procedure dispone di diverse versioni di overload, si deve avere familiarità con tutti i relativi elenchi di parametri e comprendere la modalità di risoluzione delle chiamate tra gli overload di Visual Basic. In caso contrario è possibile chiamare un overload diverso da quello previsto.  
  
 Dopo aver stabilito quale eseguire l'overload che si desidera chiamare, assicurarsi di osservare le seguenti regole:  
  
-   Specificare il numero corretto di argomenti e nell'ordine corretto.  
  
-   Idealmente, degli argomenti dovrebbero essere esattamente gli stessi dati tipi dei parametri corrispondenti. In ogni caso, il tipo di dati di ogni argomento deve ampliarsi a quello del parametro corrispondente. Ciò è vero anche con il [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) impostato su `Off`. Se un overload richiede qualsiasi conversione di narrowing dall'elenco degli argomenti, questo overload non è idoneo a essere chiamato.  
  
-   Se vengono forniti gli argomenti che richiedono l'ampliamento, verificare i tipi di dati più vicino possibile ai tipi di dati di parametro corrispondente. Se due o più overload accettano i tipi di dati di argomento, il compilatore risolve la chiamata all'overload che richiede il minor grado di ampliamento.  
  
 È possibile ridurre il rischio di mancate corrispondenze di tipo di dati utilizzando il [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) parola chiave di conversione durante la preparazione degli argomenti.  
  
### <a name="overload-resolution-failure"></a>Errore di risoluzione dell'overload  
 Quando si chiama una routine di overload, il compilatore tenta di eliminare tutti tranne uno degli overload. Se ha esito positivo, viene risolta la chiamata all'overload. Se vengono eliminati tutti gli overload o se non è possibile ridurre gli overload idonei a uno solo, viene generato un errore.  
  
 Nell'esempio seguente viene illustrato il processo di risoluzione dell'overload.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload poiché il tipo del primo argomento (`Short`) viene convertito nel tipo del parametro corrispondente (`Byte`). Viene quindi eliminato il terzo overload poiché ogni tipo di argomento nel secondo overload (`Short` e `Single`) viene ampliato al tipo corrispondente del terzo overload (`Integer` e `Single`). Il secondo overload richiede un ampliamento minore, pertanto verrà utilizzato dal compilatore per la chiamata.  
  
 Nella seconda chiamata, il compilatore non è possibile eliminare uno degli overload sulla base di restrizione. Viene eliminato il terzo overload per lo stesso motivo della prima chiamata, poiché è possibile chiamare il secondo overload con un ampliamento minore dei tipi di argomento. Tuttavia, il compilatore non è possibile risolvere tra il primo e secondo overload. Ognuno presenta un tipo di parametro definito che viene ampliato al tipo corrispondente in altro (`Byte` a `Short`, ma `Single` a `Double`). Pertanto, il compilatore genera un errore di risoluzione dell'overload.  
  
 **Approccio corretto:** per essere in grado di chiamare una routine di overload senza ambiguità, utilizzare [CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md) in modo che corrisponda ai tipi di dati di argomenti per i tipi di parametro. Nell'esempio seguente viene illustrata una chiamata a `z` che forza la risoluzione per il secondo overload.  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Risoluzione dell'overload con facoltativo e argomenti ParamArray  
 Se i due overload di una stored procedure hanno firme identiche ad eccezione del fatto che l'ultimo parametro è dichiarato [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in altro, il compilatore risolve una chiamata di procedura in base alla corrispondenza più vicina. Per ulteriori informazioni, vedere [risoluzione dell'Overload](./overload-resolution.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)  
 [Risoluzione dell'overload](./overload-resolution.md)
