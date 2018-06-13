---
title: 'Procedura: Determinare se un file è un assembly (C#)'
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: 0557f42d42e42606c3d1b2a2ad71bd797a159e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317983"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Procedura: Determinare se un file è un assembly (C#)
Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly. Per altre informazioni sugli assembly e sui metadati, vedere l'argomento [Manifesto dell'assembly](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly in modo manuale  
  
1.  Avviare il [Disassembler IL (Ildasm.exe)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Caricare il file che si intende verificare.  
  
3.  Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly. Per altre informazioni, vedere [Procedura: Visualizzare il contenuto dell'assembly](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly a livello di codice  
  
1.  Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, passando il percorso file completo e il nome del file sottoposto a test.  
  
2.  Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.  
  
```  
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
  
 Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Reflection.AssemblyName>  
 [Guida per programmatori C#](../../../../csharp/programming-guide/index.md)  
 [Assembly e Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
