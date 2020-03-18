---
title: 'Procedura: determinare se un file è un assemblyHow to: Determine if a file is an assembly'
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1d66c0c166724f195a3cafd9bcbe3c7414c08ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159507"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a>Procedura: determinare se un file è un assemblyHow to: Determine if a file is an assembly

Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly. Per ulteriori informazioni sugli assembly e sui metadati, vedere [Manifesto dell'assembly](manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly in modo manuale  
  
1. Avviare il [Disassembler IL (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2. Caricare il file che si desidera testare.  
  
3. Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly. Per ulteriori informazioni, vedere l'argomento [Procedura: visualizzare il contenuto dell'assieme](view-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly a livello di codice  
  
1. Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>, passando il percorso file completo e il nome del file sottoposto a test.  
  
2. Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.  
  
## <a name="example"></a>Esempio  
Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.  

```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  

```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```

Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.AssemblyName>
- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)
