---
title: extern (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 106ceb6a4acf57daa01919acb38e4245655fca2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="extern-c-reference"></a>extern (Riferimenti per C#)
Il modificatore `extern` consente di dichiarare un metodo implementato esternamente. Il modificatore `extern` viene utilizzato in genere con l'attributo `DllImport` quando si effettua una chiamata in codice non gestito tramite i servizi di interoperabilità. In questo caso, anche il metodo deve essere dichiarato come `static`, come illustrato nell'esempio seguente:  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 La parola chiave `extern` può definire anche un alias di assembly esterno, rendendo possibile il riferimento a versioni diverse dello stesso componente dall'interno di un unico assembly. Per altre informazioni, vedere [alias esterno](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 È errato usare i modificatori [abstract](../../../csharp/language-reference/keywords/abstract.md) e `extern` contemporaneamente per modificare lo stesso membro. L'utilizzo del modificatore `extern` indica che il metodo viene implementato all'esterno del codice C#, mentre l'utilizzo del modificatore `abstract` indica che l'implementazione del metodo non viene fornita nella classe.  
  
 La parola chiave extern ha un utilizzo più limitato in c# rispetto a C++. Per confrontare la parola chiave C# con la parola chiave C++, vedere Utilizzo di extern per specificare il collegamento in Riferimenti al linguaggio C++.  
  
## <a name="example"></a>Esempio  
 **Esempio 1.** In questo esempio il programma riceve una stringa dall'utente e la visualizza in una finestra di messaggio. Il programma utilizza il metodo `MessageBox` importato dalla libreria User32.dll.  
  
 [!code-csharp[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## <a name="example"></a>Esempio  
 **Esempio 2.** In questo esempio viene illustrato un programma C# che chiama una libreria C (una DLL nativa).  
  
 1. Creare il seguente file C e denominarlo `cmdll.c`:  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a>Esempio  
 2. Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32 dalla directory di installazione di Visual Studio e compilare il file `cmdll.c` digitando **cl /LD cmdll.c** al prompt dei comandi.  
  
 3. Nella stessa directory creare il seguente file C# e denominarlo `cm.cs`:  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a>Esempio  
 3. Aprire una finestra del prompt dei comandi degli strumenti nativi di Visual Studio x64 o x32) dalla directory di installazione di Visual Studio e compilare il file `cm.cs` digitando:  
  
> **csc cm.cs** (al prompt dei comandi x64)   
>  -oppure-  
> **csc /platform:x86 cm.cs** (al prompt dei comandi x32)  
  
 Verrà creato il file eseguibile `cm.exe`.  
  
 4. Eseguire `cm.exe`. Il metodo `SampleMethod` passa il valore 5 al file DLL, che restituisce il valore moltiplicato per 10.  Il programma produce l'output seguente:  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)
