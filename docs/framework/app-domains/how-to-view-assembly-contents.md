---
title: 'Procedura: Visualizzare il contenuto dell&quot;assembly | Microsoft Docs'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 38ed309c8d1ef7467b235eb2e751ffb9016a83ab
ms.contentlocale: it-it
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-view-assembly-contents"></a>Procedura: Visualizzare il contenuto dell'assembly
È possibile usare [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni di Microsoft Intermediate Language (MSIL) in un file. Se il file esaminato è un assembly, è possibile che le informazioni includano gli attributi dell'assembly, oltre a riferimenti ad altri moduli e assembly. Queste informazioni possono risultare utili nel determinare se un file è un assembly o se è parte di un assembly e se il file contiene riferimenti ad altri moduli o assembly.  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a>Per visualizzare il contenuto di un assembly usando Ildasm.exe  
  
1.  Al prompt dei comandi digitare **ildasm** \<*nome assembly*>. Ad esempio, il comando seguente esegue il disassemblaggio dell'assembly `Hello.exe`.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a>Per visualizzare informazioni del manifesto dell'assembly  
  
1.  Fare doppio clic sull'icona MANIFESTO nella finestra Disassembler MSIL.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente avvia un programma "Hello, World" di base. Dopo aver compilato il programma usare Ildasm.exe per disassemblare l'assembly Hello.exe e visualizzarne il manifesto.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Se si esegue il comando ildasm.exe nell'assembly Hello.exe e si fa doppio clic sull'icona MANIFESTO nella finestra IL DASM, viene prodotto l'output seguente:  
  
```  
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
  
 La tabella seguente descrive ogni direttiva del manifesto dell'assembly relativo all'assembly Hello.exe usato nell'esempio.  
  
|Direttiva|Descrizione|  
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
  
 Il manifesto di un assembly può contenere diverse direttive, a seconda del contenuto dell'assembly. Per un elenco completo delle direttive del manifesto dell'assembly, vedere la documentazione ECMA, in particolare "Partition II: Metadata Definition and Semantics" (Partizione II: Definizione dei metadati e semantica) e "Partition III: CIL Instruction Set" (Partizione III: Set di istruzioni CIL). La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.  
  
## <a name="see-also"></a>Vedere anche  
 [Domini applicazione e assembly](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)   
 [Argomenti relativi alle procedure per domini applicazione e assembly](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)   
 [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)

