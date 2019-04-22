---
title: Risoluzione dei problemi relativi alle matrici (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833373"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Risoluzione dei problemi relativi alle matrici (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si lavora con le matrici.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errori di compilazione, la dichiarazione e inizializzazione di una matrice  
 Errori di compilazione possono essere generati da malintesi delle regole per la dichiarazione, la creazione e inizializzazione di matrici. Le cause più comuni degli errori sono i seguenti:  
  
-   Fornendo una [operatore New](../../../../visual-basic/language-reference/operators/new-operator.md) clausola dopo aver specificato le lunghezze delle dimensioni nella dichiarazione di variabile di matrice. Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Specifica le lunghezze delle dimensioni per più di una matrice di primo livello di una matrice di matrici. La riga di codice seguente mostra una dichiarazione non valida di questo tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   L'omissione di `New` parola chiave quando si specificano i valori degli elementi. La riga di codice seguente mostra una dichiarazione non valida di questo tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Fornendo una `New` clausola senza parentesi graffe (`{}`). Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>L'accesso a una matrice fuori intervallo  
 Il processo di inizializzazione matrice assegna un limite superiore e inferiore di ogni dimensione. Ogni accesso a un elemento della matrice debba specificare un indice valido o indice, per ogni dimensione. Se il valore dell'indice è di sotto del limite inferiore o di sopra del limite superiore, un <xref:System.IndexOutOfRangeException> dei risultati dell'eccezione. Il compilatore non è in grado di rilevare un errore di questo tipo, in modo che si verifica un errore in fase di esecuzione.  
  
### <a name="determining-bounds"></a>Determinazione dei limiti  
 Se un altro componente passa una matrice al codice, ad esempio come un argomento di routine, non si conosce la dimensione della matrice o le lunghezze delle dimensioni. È sempre necessario determinare il limite massimo per ogni dimensione di matrice prima di tentare di accedere a tutti gli elementi. Se la matrice è stata creata da alcuni mezzi diversi da Visual Basic `New` clausola, potrebbe essere un valore diverso da 0 al limite inferiore ed è più sicuro determinare anche tale limite inferiore.  
  
### <a name="specifying-the-dimension"></a>Specificare la dimensione di tipo  
 Quando si determinano i limiti di una matrice multidimensionale, prestare attenzione a come specificare la dimensione. Il `dimension` parametri del <xref:System.Array.GetLowerBound%2A> e <xref:System.Array.GetUpperBound%2A> metodi sono basati su 0, mentre il `Rank` parametri di Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> e <xref:Microsoft.VisualBasic.Information.UBound%2A> funzioni sono basate su 1.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Procedura: Inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
