---
title: Risoluzione dei problemi relativi alle matrici
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: e633c5a00693f188270b1610abaf2decb656b00a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414595"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Risoluzione dei problemi relativi alle matrici (Visual Basic)
In questa pagina vengono elencati alcuni problemi comuni che possono verificarsi quando si utilizzano matrici.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errori di compilazione che dichiarano e inizializzano una matrice  
 Gli errori di compilazione possono derivare dalla comprensione delle regole per la dichiarazione, la creazione e l'inizializzazione di matrici. Di seguito sono riportate le cause più comuni degli errori:  
  
- Fornire una [nuova clausola operator](../../../language-reference/operators/new-operator.md) dopo aver specificato le lunghezze della dimensione nella dichiarazione della variabile di matrice. Nelle righe di codice seguenti vengono mostrate dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Specifica delle lunghezze delle dimensioni per più della matrice di primo livello di una matrice irregolare. La seguente riga di codice mostra una dichiarazione non valida di questo tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Omissione della `New` parola chiave quando si specificano i valori dell'elemento. La seguente riga di codice mostra una dichiarazione non valida di questo tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Specifica di una `New` clausola senza parentesi graffe ( `{}` ). Nelle righe di codice seguenti vengono mostrate dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Accesso a una matrice fuori limite  
 Il processo di inizializzazione di una matrice assegna un limite superiore e un limite inferiore a ogni dimensione. Tutti gli accessi a un elemento della matrice devono specificare un indice valido, o pedice, per ogni dimensione. Se un indice è al di sotto del limite inferiore o al di sopra del limite superiore, viene generata un' <xref:System.IndexOutOfRangeException> eccezione. Il compilatore non è in grado di rilevare tale errore, quindi si verifica un errore in fase di esecuzione.  
  
### <a name="determining-bounds"></a>Determinazione dei limiti  
 Se un altro componente passa una matrice al codice, ad esempio come argomento di routine, non si conosce la dimensione della matrice o la lunghezza delle relative dimensioni. Prima di provare ad accedere a qualsiasi elemento, è necessario determinare sempre il limite superiore per ogni dimensione di una matrice. Se la matrice è stata creata con un mezzo diverso da una `New` clausola Visual Basic, il limite inferiore potrebbe essere diverso da 0 ed è più sicuro determinare anche tale limite inferiore.  
  
### <a name="specifying-the-dimension"></a>Specifica della dimensione  
 Quando si determinano i limiti di una matrice multidimensionale, prestare attenzione alla modalità di impostazione della dimensione. I `dimension` parametri dei <xref:System.Array.GetLowerBound%2A> metodi e <xref:System.Array.GetUpperBound%2A> sono basati su 0, mentre i `Rank` parametri del Visual Basic e delle <xref:Microsoft.VisualBasic.Information.LBound%2A> <xref:Microsoft.VisualBasic.Information.UBound%2A> funzioni sono in base 1.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](index.md)
- [Procedura: Inizializzare una variabile di matrice in Visual Basic](how-to-initialize-an-array-variable.md)
