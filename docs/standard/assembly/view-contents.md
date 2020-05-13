---
title: "Procedura: visualizzare il contenuto dell'assembly"
description: È possibile usare il disassembler IL per visualizzare gli attributi e i riferimenti di un assembly ad altri moduli e assembly.
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
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: aed490459252466c6da06e5422b83b1bc20fb885
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380061"
---
# <a name="how-to-view-assembly-contents"></a>Procedura: visualizzare il contenuto dell'assembly

È possibile usare [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni di Microsoft Intermediate Language (MSIL) in un file. Se il file esaminato è un assembly, queste informazioni possono includere gli attributi dell'assembly e i riferimenti ad altri moduli e assembly. Queste informazioni possono essere utili per determinare se un file è un assembly o una parte di un assembly e se il file contiene riferimenti ad altri moduli o assembly.

Per visualizzare il contenuto di un assembly tramite *Ildasm. exe*, immettere **il \< nome dell'assembly Ildasm>** al prompt dei comandi. Ad esempio, il comando seguente Disassembla l'assembly *Hello. exe* .

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

Nella tabella seguente vengono descritte le singole direttive del manifesto dell'assembly dell'assembly *Hello. exe* utilizzato nell'esempio:

|Direttiva|Description|
|---------------|-----------------|
|**. assembly extern \< nome assembly>**|Specifica un altro assembly contenente elementi a cui il modulo corrente fa riferimento (in questo esempio `mscorlib`).|
|**\<>token. PublicKeyToken**|Specifica il token della chiave effettiva dell'assembly a cui viene fatto riferimento.|
|**. ver \< numero di versione>**|Specifica il numero di versione dell'assembly a cui viene fatto riferimento.|
|**. \< nome assembly assembly>**|Specifica il nome dell'assembly.|
|**. valore Int32 dell'algoritmo hash \<>**|Specifica l'algoritmo hash usato.|
|**. ver \< numero di versione>**|Specifica il numero di versione dell'assembly.|
|**\<nome file. modulo>**|Specifica il nome dei moduli che costituiscono l'assembly. In questo esempio l'assembly è costituito da un unico file.|
|**. valore del sottosistema \<>**|Specifica l'ambiente di applicazione necessario per il programma. In questo esempio il valore 3 indica che il file eseguibile viene eseguito da una console.|
|**.corflags**|Attualmente, campo riservato nei metadati.|

Il manifesto di un assembly può contenere diverse direttive, a seconda del contenuto dell'assembly. Per un elenco completo delle direttive nel manifesto dell'assembly, vedere la documentazione relativa a ECMA, in particolare "Partition II: Metadata Definition and Semantics" e "Partition III: CIL instruction set":

- [Standard ECMA C# e Common Language Infrastructure](../components.md#applicable-standards)
- [ECMA-335-Common Language Infrastructure standard (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a>Vedere anche

- [Domini applicazione e assembly](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [Procedure per i domini applicazione e gli assembly](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [Ildasm. exe (disassembler IL)](../../framework/tools/ildasm-exe-il-disassembler.md)
