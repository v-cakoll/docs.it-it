---
title: 'Procedura: Visualizza contenuto assembly'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
author: rpetrusha
ms.author: ronpet
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 8f27afafde0b83dfe886d218f3148d8ff07b30cb
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973026"
---
# <a name="how-to-view-assembly-contents"></a>Procedura: Visualizza contenuto assembly
È possibile usare [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni di Microsoft Intermediate Language (MSIL) in un file. Se il file esaminato è un assembly, è possibile che le informazioni includano gli attributi dell'assembly, oltre a riferimenti ad altri moduli e assembly. Queste informazioni possono risultare utili nel determinare se un file è un assembly o se è parte di un assembly e se il file contiene riferimenti ad altri moduli o assembly.  
  
Per visualizzare il contenuto di un assembly tramite *Ildasm. exe*, digitare **Ildasm** \< *assembly name*> al prompt dei comandi. Ad esempio, il comando seguente Disassembla l'assembly *Hello. exe* .  

```cmd
ildasm Hello.exe  
```  

Per visualizzare le informazioni del manifesto dell'assembly, fare doppio clic sull'icona del **manifesto** nella finestra del disassembler MSIL.  
  
## <a name="example"></a>Esempio  
L'esempio seguente inizia con un programma "Hello World" di base. Dopo la compilazione del programma, utilizzare *Ildasm. exe* per disassemblare l'assembly *Hello. exe* e visualizzare il manifesto dell'assembly.  

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Imports System

Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

Se si esegue il comando *Ildasm. exe* nell'assembly *Hello. exe* e si fa doppio clic sull'icona del **manifesto** nella finestra del disassembler MSIL, viene prodotto l'output seguente:  

```output
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 Nella tabella seguente vengono descritte le singole direttive del manifesto dell'assembly dell'assembly *Hello. exe* utilizzato nell'esempio.  
  
|Direttiva|DESCRIZIONE|  
|---------------|-----------------|  
|**.assembly extern \<** *nome assembly* **>**|Specifica un altro assembly contenente elementi a cui il modulo corrente fa riferimento (in questo esempio `mscorlib`).|  
|**.publickeytoken \<** *token* **>**|Specifica il token della chiave effettiva dell'assembly a cui viene fatto riferimento.|  
|**.ver \<** *numero versione* **>**|Specifica il numero di versione dell'assembly a cui viene fatto riferimento.|  
|**.assembly \<** *nome assembly* **>**|Specifica il nome dell'assembly.|  
|**.hash algorithm \<** *valore int32* **>**|Specifica l'algoritmo hash usato.|  
|**.ver \<** *numero versione* **>**|Specifica il numero di versione dell'assembly.|  
|**.module \<** *nome file* **>**|Specifica il nome dei moduli che costituiscono l'assembly. In questo esempio l'assembly è costituito da un unico file.|  
|**.subsystem \<** *valore* **>**|Specifica l'ambiente di applicazione necessario per il programma. In questo esempio il valore 3 indica che il file eseguibile viene eseguito da una console.|  
|**.corflags**|Attualmente, campo riservato nei metadati.|  
  
 Il manifesto di un assembly può contenere diverse direttive, a seconda del contenuto dell'assembly. Per un elenco completo delle direttive del manifesto dell'assembly, vedere la documentazione ECMA, in particolare "Partition II: Metadata Definition and Semantics" e "Partition III: Set di istruzioni CIL ". La documentazione è disponibile online. Vedere [gli C# standard ECMA e Common Language Infrastructure](https://go.microsoft.com/fwlink/?LinkID=99212) su MSDN e [standard ECMA-335-Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web di ECMA International.  
  
## <a name="see-also"></a>Vedere anche

- [Domini applicazione e assembly](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [Procedure per i domini applicazione e gli assembly](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [Ildasm.exe (Disassembler IL)](../../framework/tools/ildasm-exe-il-disassembler.md)
