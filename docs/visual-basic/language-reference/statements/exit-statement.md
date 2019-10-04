---
title: Istruzione Exit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956938"
---
# <a name="exit-statement-visual-basic"></a>Istruzione Exit (Visual Basic)

Esce da una routine o da un blocco e trasferisce immediatamente il controllo all'istruzione successiva alla chiamata di routine o alla definizione del blocco.

## <a name="syntax"></a>Sintassi

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>Istruzioni

 `Exit Do`  
 Chiude immediatamente il ciclo `Do` in cui viene visualizzato. L'esecuzione continua con l'istruzione che segue l'istruzione `Loop`. `Exit Do` può essere utilizzato solo all'interno di un ciclo `Do`. Quando viene usato all'interno di cicli `Do` annidati, `Exit Do` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.

 `Exit For`  
 Chiude immediatamente il ciclo `For` in cui viene visualizzato. L'esecuzione continua con l'istruzione che segue l'istruzione `Next`. `Exit For` può essere utilizzato solo all'interno di un ciclo `For`... `Next` o `For Each`... `Next`. Quando viene usato all'interno di cicli `For` annidati, `Exit For` esce dal ciclo più interno e trasferisce il controllo al livello di nidificazione successivo.

 `Exit Function`  
 Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata. L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Function`. `Exit Function` può essere utilizzato solo all'interno di una procedura `Function`.

 Per specificare un valore restituito, è possibile assegnare il valore al nome della funzione in una riga prima dell'istruzione `Exit Function`. Per assegnare il valore restituito e uscire dalla funzione in un'unica istruzione, è possibile usare invece l' [istruzione return](return-statement.md).

 `Exit Property`  
 Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata. L'esecuzione continua con l'istruzione che ha chiamato la procedura `Property`, ovvero con l'istruzione che richiede o imposta il valore della proprietà. `Exit Property` può essere utilizzato solo all'interno di una routine `Get` o `Set` di una proprietà.

 Per specificare un valore restituito in una procedura `Get`, è possibile assegnare il valore al nome della funzione su una riga prima dell'istruzione `Exit Property`. Per assegnare il valore restituito e uscire dalla procedura `Get` in un'unica istruzione, è possibile usare invece l'istruzione `Return`.

 In una procedura `Set`, l'istruzione `Exit Property` è equivalente all'istruzione `Return`.

 `Exit Select`  
 Esce immediatamente dal blocco `Select Case` in cui viene visualizzato. L'esecuzione continua con l'istruzione che segue l'istruzione `End Select`. `Exit Select` può essere utilizzato solo all'interno di un'istruzione `Select Case`.

 `Exit Sub`  
 Esce immediatamente dalla procedura @no__t 0 in cui viene visualizzata. L'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la procedura `Sub`. `Exit Sub` può essere utilizzato solo all'interno di una procedura `Sub`.

 In una procedura `Sub`, l'istruzione `Exit Sub` è equivalente all'istruzione `Return`.

 `Exit Try`  
 Esce immediatamente dal blocco `Try` o `Catch` in cui viene visualizzato. L'esecuzione continua con il blocco `Finally` se ne esiste uno oppure con l'istruzione che segue l'istruzione `End Try` in caso contrario. `Exit Try` può essere utilizzato solo all'interno di un blocco `Try` o `Catch`, non all'interno di un blocco `Finally`.

 `Exit While`  
 Chiude immediatamente il ciclo `While` in cui viene visualizzato. L'esecuzione continua con l'istruzione che segue l'istruzione `End While`. `Exit While` può essere utilizzato solo all'interno di un ciclo `While`. Quando viene utilizzato all'interno di cicli `While` annidati, `Exit While` trasferisce il controllo al ciclo che è un livello annidato sopra il ciclo in cui si verifica `Exit While`.

## <a name="remarks"></a>Note

Non confondere le istruzioni `Exit` con le istruzioni `End`. `Exit` non definisce la fine di un'istruzione.

## <a name="example"></a>Esempio

Nell'esempio seguente, la condizione del ciclo arresta il ciclo quando la variabile `index` è maggiore di 100. L'istruzione `If` del ciclo, tuttavia, fa sì che l'istruzione `Exit Do` interrompa il ciclo quando la variabile di indice è maggiore di 10.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene assegnato il valore restituito al nome della funzione `myFunction`, quindi viene utilizzato `Exit Function` per restituire dalla funzione:

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l' [istruzione return](return-statement.md) per assegnare il valore restituito e uscire dalla funzione:

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Continue](continue-statement.md)
- [Istruzione Do...Loop](do-loop-statement.md)
- [Istruzione End](end-statement.md)
- [Istruzione For Each...Next](for-each-next-statement.md)
- [Istruzione For...Next](for-next-statement.md)
- [Istruzione Function](function-statement.md)
- [Istruzione Return](return-statement.md)
- [Istruzione Stop](stop-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
