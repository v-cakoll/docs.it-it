---
title: Strutture e altri elementi di programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266859"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Strutture e altri elementi di programmazione (Visual Basic)
È possibile utilizzare le strutture in combinazione con matrici, oggetti e procedure, nonché tra loro. Le interazioni usano la stessa sintassi utilizzata da questi elementi singolarmente.  
  
> [!NOTE]
> Non è possibile inizializzare nessuno degli elementi della struttura nella dichiarazione della struttura. È possibile assegnare valori solo agli elementi di una variabile dichiarata come di un tipo di struttura.  
  
## <a name="structures-and-arrays"></a>Strutture e matrici  
 Una struttura può contenere una matrice come uno o più dei relativi elementi. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 È possibile accedere ai valori di una matrice all'interno di una struttura nello stesso modo in cui si accede a una proprietà in un oggetto. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 È inoltre possibile dichiarare una matrice di strutture. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Seguire le stesse regole per accedere ai componenti di questa architettura di dati. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Strutture e oggetti  
 Una struttura può contenere un oggetto come uno o più dei suoi elementi. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 È necessario utilizzare una classe di oggetti `Object`specifica in una dichiarazione di questo tipo, anziché .  
  
## <a name="structures-and-procedures"></a>Strutture e procedure  
 È possibile passare una struttura come argomento di routine. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Nell'esempio precedente viene passata la struttura *per riferimento*, che consente alla routine di modificarne gli elementi in modo che le modifiche abbiano effetto nel codice chiamante. Se si desidera proteggere una struttura da tale modifica, passarla per valore.  
  
 È inoltre possibile restituire `Function` una struttura da una routine. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>Strutture all'interno delle strutture  
 Le strutture possono contenere altre strutture. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 È inoltre possibile utilizzare questa tecnica per incapsulare una struttura definita in un modulo all'interno di una struttura definita in un modulo diverso.  
  
 Le strutture possono contenere altre strutture a una profondità arbitraria.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Variabili di struttura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)
