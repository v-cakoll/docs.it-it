---
title: Risoluzione dell'overload (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- overload resolution
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedure overloading [Visual Basic], overload resolution
- signatures [Visual Basic], procedure
- overloads [Visual Basic], resolution
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
ms.openlocfilehash: 734cc521fe2e8b7af5ca594ced8c3a0a22603af7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525950"
---
# <a name="overload-resolution-visual-basic"></a>Risoluzione dell'overload (Visual Basic)
Quando il compilatore Visual Basic rileva una chiamata a una routine definito in numerose versioni di overload, il compilatore deve decidere quale overload da chiamare. A tale scopo, seguire questa procedura:  
  
1.  **Accessibilità.** Elimina tutti gli overload con un livello di accesso che impedisce che il codice chiamante viene chiamata.  
  
2.  **Numero di parametri.** Elimina qualsiasi overload che definisce un numero di parametri diverso rispetto a quello fornito nella chiamata.  
  
3.  **Tipi di dati di parametro.** Il compilatore assegna la priorità di metodi di istanza rispetto ai metodi di estensione. Se viene trovato alcun metodo di istanza che richiede solo di ampliamento per rispondere alla chiamata di procedura, vengono eliminati tutti i metodi di estensione e il compilatore continua con solo i candidati dei metodi di istanza. Se non viene trovato alcun metodo di tale istanza, continua con l'istanza sia i metodi di estensione.  
  
     In questo passaggio elimina alcun overload per il quale i tipi di dati degli argomenti di chiamata non convertibili nei tipi di parametro definiti in overload.  
  
4.  **Conversioni di Narrowing.** Elimina qualsiasi overload che richiede una conversione narrowing dai tipi di argomento chiamante per i tipi di parametro definiti. Ciò è vero se il controllo del tipo di opzione ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) viene `On` o `Off`.  
  
5.  **Widening minimi.** Il compilatore prende in considerazione gli overload rimanenti nelle coppie. Per ogni coppia, confronta i tipi di dati dei parametri definiti. Se i tipi in uno degli overload tutti vengano ampliati ai tipi corrispondenti in altra, il compilatore consente di eliminare quest'ultimo. Vale a dire, viene mantenuto l'overload che richiede una quantità minima di ampliamento.  
  
6.  **Singola candidato.** Vengono presi in considerazione gli overload nelle coppie finché l'unico overload rimane impostato su e la chiamata a tale overload viene risolta. Se il compilatore non è possibile ridurre gli overload a uno solo, viene generato un errore.  
  
 Nella figura seguente viene illustrato il processo che determina quale versione di un set di versioni di overload da chiamare.  
  
 ![Diagramma di flusso del processo di risoluzione dell'overload](./media/overloadres.gif "OverloadRes")  
La risoluzione tra le versioni di overload  
  
 L'esempio seguente illustra questo processo di risoluzione dell'overload.  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 Nella prima chiamata, il compilatore elimina il primo overload, perché il tipo del primo argomento (`Short`) viene convertito nel tipo del parametro corrispondente (`Byte`). Il terzo overload viene quindi eliminato poiché ogni tipo di argomento nel secondo overload (`Short` e `Single`) viene ampliato al tipo del terzo overload corrispondente (`Integer` e `Single`). Il secondo overload richiede un ampliamento minore, in modo che il compilatore lo usa per la chiamata.  
  
 Nella seconda chiamata, il compilatore non è possibile eliminare uno degli overload sulla base di restrizione. Elimina il terzo overload per lo stesso motivo della prima chiamata, perché può chiamare il secondo overload con meno di ampliamento dei tipi di argomento. Tuttavia, il compilatore non può risolvere tra i primi e il secondo overload. Ognuno ha un tipo di parametro definito che viene ampliato al tipo corrispondente in altro (`Byte` al `Short`, ma `Single` a `Double`). Di conseguenza, il compilatore genera un errore di risoluzione dell'overload.  
  
## <a name="overloaded-optional-and-paramarray-arguments"></a>Sottoposto a overload facoltativa e argomenti ParamArray  
 Se due overload di una stored procedure hanno firme identiche ad eccezione del fatto che l'ultimo parametro viene dichiarato [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in uno e [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in altro, il compilatore risolve una chiamata a questa procedura come di seguito:  
  
|Se la chiamata viene fornito come ultimo argomento|Il compilatore risolve la chiamata all'overload dichiara come ultimo argomento|  
|---|---|  
|Nessun valore (argomento omesso)|`Optional`|  
|Un singolo valore|`Optional`|  
|Due o più valori in un elenco delimitato da virgole|`ParamArray`|  
|Matrice di qualsiasi lunghezza (tra cui una stringa vuota)|`ParamArray`|  
  
## <a name="see-also"></a>Vedere anche
- [Parametri facoltativi](./optional-parameters.md)
- [Matrici di parametri](./parameter-arrays.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Procedura: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Metodi di estensione](./extension-methods.md)
