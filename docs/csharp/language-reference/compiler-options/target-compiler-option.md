---
title: -target (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target
dev_langs:
- CSharp
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 22dc86ce0c0a24681d05e54e5f1ba4f36295659a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="target-c-compiler-options"></a>/target (opzioni del compilatore C#)
L'opzione del compilatore **/target** può essere specificata in uno dei quattro moduli seguenti:  
  
 [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 Per creare un file con estensione exe per le applicazioni [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].  
  
 [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Per creare un file con estensione exe.  
  
 [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Per creare una libreria di codice.  
  
 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Per creare un modulo.  
  
 [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Per creare un programma di Windows.  
  
 [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Per creare un file con estensione winmdobj intermedio.  
  
 Se non si specifica **/target: module**, **/target** provoca l'inserimento di un manifesto dell'assembly di .NET Framework in un file di output. Per altre informazioni, vedere [Assembly in Common Language Runtime](https://msdn.microsoft.com/library/k3677y81) e [Attributi comuni](http://msdn.microsoft.com/library/2f48a7ec-9683-4899-a1d2-a08be8fc558b).  
  
 Il manifesto dell'assembly viene inserito nel primo file di output con estensione .exe della compilazione o nel primo DLL, se non esiste alcun file di output .exe. Ad esempio, nella riga di comando seguente il manifesto verrà inserito in `1.exe`:  
  
```console  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 Il compilatore crea solo un manifesto dell'assembly per ogni compilazione. Le informazioni su tutti i file in una compilazione vengono inserite nel manifesto dell'assembly. Tutti i file di output, ad eccezione di quelli creati con **/target:module** possono contenere un manifesto dell'assembly. Quando si generano più file di output nella riga di comando, è possibile creare solo un manifesto e deve essere inseriti nel primo file di output specificato nella riga di comando. Indipendentemente da quale sia il primo file di output (**/target:exe**, **/target:winexe**, **/target:library** o **/target:module**), tutti gli altri file di output generati nella stessa compilazione devono essere moduli (**/target:module**).  
  
 Se si crea un assembly, è possibile indicare che tutto o parte del codice è conforme a CLS con l'attributo <xref:System.CLSCompliantAttribute>.  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Per altre informazioni sull'impostazione di questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)   
 [-subsystemversion (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)

