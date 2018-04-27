---
title: Risoluzione dei problemi relativi alle matrici (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e5c00c2b531dd019a207b16ffcac95424bfe450
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-arrays-visual-basic"></a>Risoluzione dei problemi relativi alle matrici (Visual Basic)
Questa pagina elenca alcuni problemi comuni che possono verificarsi quando si lavora con le matrici.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errori di compilazione, la dichiarazione e inizializzazione di una matrice  
 Errori di compilazione possono essere generati da malinteso delle regole per la dichiarazione, la creazione e inizializzazione di matrici. Le cause più comuni di errori sono i seguenti:  
  
-   Fornisce un [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) clausola dopo aver specificato le lunghezze delle dimensioni nella dichiarazione di variabile di matrice. Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Specifica le lunghezze della dimensione per più di una matrice di primo livello di una matrice di matrici. L'esempio di codice seguente viene illustrata una dichiarazione di questo tipo non valida.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   L'omissione di `New` parola chiave quando si specificano i valori degli elementi. L'esempio di codice seguente viene illustrata una dichiarazione di questo tipo non valida.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Fornisce un `New` clausola senza parentesi graffe (`{}`). Le righe di codice seguente mostrano le dichiarazioni non valide di questo tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>L'accesso a una matrice fuori dai limiti  
 Il processo di inizializzazione di una matrice assegna un limite superiore e inferiore a ogni dimensione. Ogni accesso a un elemento della matrice debba specificare un indice valido o un indice, per ogni dimensione. Se il valore dell'indice è di sotto del limite inferiore o di sopra del limite superiore, un <xref:System.IndexOutOfRangeException> risultati dell'eccezione. Il compilatore non è in grado di rilevare un errore, si verifica un errore in fase di esecuzione.  
  
### <a name="determining-bounds"></a>Definizione di limiti  
 Se un altro componente passa una matrice al codice, ad esempio come un argomento di routine, non si conosce la dimensione della matrice o le lunghezze delle dimensioni. Prima di tentare di accedere a tutti gli elementi, è sempre necessario determinare il limite superiore per tutte le dimensioni di una matrice. Se la matrice è stata creata con mezzi diversi da Visual Basic `New` -clausola, il limite inferiore potrebbe essere un valore diverso da 0 ed è più sicuro determinare anche tale limite inferiore.  
  
### <a name="specifying-the-dimension"></a>Specifica la dimensione  
 Quando si determinano i limiti di una matrice multidimensionale, prestare attenzione a come specificare la dimensione. Il `dimension` parametri del <xref:System.Array.GetLowerBound%2A> e <xref:System.Array.GetUpperBound%2A> metodi sono basate su 0, mentre il `Rank` parametri di Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> e <xref:Microsoft.VisualBasic.Information.UBound%2A> funzioni sono basati su 1.  
  
## <a name="see-also"></a>Vedere anche  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Procedura: Inizializzare una variabile di matrice in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
