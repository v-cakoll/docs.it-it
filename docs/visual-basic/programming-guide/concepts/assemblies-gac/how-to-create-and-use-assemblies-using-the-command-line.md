---
title: 'Procedura: creare e utilizzare assembly dalla riga di comando (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 72f3e91f9fb88019f937dcd281aa14ab4e887daf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Procedura: creare e utilizzare assembly dalla riga di comando (Visual Basic)
Un assembly, o libreria a collegamento dinamico (DLL), viene collegato al programma in fase di esecuzione. Per illustrare la creazione e l'uso di una DLL, si consideri lo scenario seguente:  
  
-   `MathLibrary.DLL`: il file libreria che contiene i metodi da chiamare in fase di esecuzione. In questo esempio la DLL contiene due metodi: `Add` e `Multiply`.  
  
-   `Add`: il file di origine che contiene il metodo `Add`. Restituisce la somma dei suoi parametri. La classe `AddClass` che contiene il metodo `Add` è un membro dello spazio dei nomi `UtilityMethods`.  
  
-   `Mult`: il codice sorgente che contiene il metodo `Multiply`. Restituisce il prodotto dei suoi parametri. Anche la classe `MultiplyClass` che contiene il metodo `Multiply` è un membro dello spazio dei nomi `UtilityMethods`.  
  
-   `TestCode`: il file che contiene il metodo `Main`. Usa i metodi del file DLL per calcolare la somma e il prodotto degli argomenti in fase di esecuzione.  
  
## <a name="example"></a>Esempio  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 Questo file contiene l'algoritmo che usa i metodi della DLL: `Add` e `Multiply`. Inizia con l'analisi degli argomenti immessi dalla riga di comando: `num1` e `num2`. Quindi calcola la somma usando il metodo `Add` sulla classe `AddClass` e il prodotto usando il metodo `Multiply` sulla classe `MultiplyClass`.  
  
 Si noti che il `Imports` istruzione all'inizio del file consente di utilizzare i nomi di classe non qualificati per fare riferimento ai metodi della DLL in fase di compilazione, come indicato di seguito:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 In caso contrario è necessario usare nomi completi, come indicato di seguito:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Esecuzione  
 Per eseguire il programma immettere il nome del file EXE, seguito da due numeri, come indicato di seguito:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il file `MathLibrary.DLL`, compilare i due file `Add` e `Mult` usando la seguente riga di comando.  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 Il [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) l'opzione del compilatore indica al compilatore di generare un file DLL anziché un file EXE. Il [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) opzione seguita da un nome di file utilizzato per specificare il nome del file DLL. In caso contrario il compilatore usa il primo file (`Add.vb`) come nome della DLL.  
  
 Per compilare il file eseguibile, `TestCode.exe`, usare la seguente riga di comando:  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 L'opzione **/out** del compilatore indica al compilatore di generare un file EXE e specifica il nome del file che deve essere generato (`TestCode.exe`). Questa opzione del compilatore è opzionale. Il [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) i file DLL che utilizza questo programma consente di specificare l'opzione del compilatore.  
  
 Per ulteriori informazioni sulla compilazione dalla riga di comando, vedere e [compilazione dalla riga di comando](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)  
 [Assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Creazione di una classe che contenga le funzioni DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
