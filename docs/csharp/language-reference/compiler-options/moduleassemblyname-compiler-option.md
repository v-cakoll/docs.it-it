---
title: -moduleassemblyname (opzione del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8ebd6f7498adead4586c9e90ec58ca8efe81aaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname-c-compiler-option"></a>/moduleassemblyname (opzione del compilatore C#)
Specifica l'assembly i cui tipi non pubblici sono accessibili da un file con estensione NETMODULE.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argomenti  
 `assembly_name`  
 Nome dell'assembly i cui tipi non pubblici sono accessibili dal file con estensione netmodule.  
  
## <a name="remarks"></a>Note  
 **/moduleassemblyname** deve essere usato quando si compila un file con estensione netmodule e vengono soddisfatte le condizioni seguenti:  
  
-   Tramite il file con estensione netmodule deve essere possibile accedere a tipi non pubblici in un assembly esistente.  
  
-   L'utente conosce il nome dell'assembly in cui verrà compilato il file con estensione netmodule.  
  
-   L'assembly esistente ha concesso l'accesso assembly Friend all'assembly in cui verrà compilato il file con estensione netmodule.  
  
 Per altre informazioni sulla compilazione di un file con estensione netmodule, vedere [/target:module (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Per altre informazioni sugli assembly Friend, vedere [Assembly Friend ](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
 L'opzione non è disponibile all'interno dell'ambiente di sviluppo, ma soltanto durante la compilazione dalla riga di comando.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene generato un assembly con un tipo privato e viene concesso all'assembly Friend l'accesso a un assembly denominato csman_an_assembly.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene compilato un file con estensione netmodule tramite cui si accede a un tipo non pubblico nel file moduleassemblyname_1.dll dell'assembly. Sapendo che questo file con estensione netmodule verrà compilato in un assembly denominato csman_an_assembly, è possibile specificare **/moduleassemblyname** per consentire al file con estensione netmodule di accedere a tipi non pubblici nell'assembly che ha concesso all'assembly Friend l'accesso a csman_an_assembly.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio di codice viene compilato l'assembly csman_an_assembly, facendo riferimento all'assembly e al file con estensione netmodule compilati in precedenza.  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 **An_Internal_Class.Test called**  
## <a name="see-also"></a>Vedere anche  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
