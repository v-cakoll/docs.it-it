---
title: 'Procedura: Creare un assembly su più file'
description: Informazioni su come compilare (creare) un assembly su più file in .NET usando il codice di esempio per illustrare ogni passaggio della procedura.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: a4c298284950ba2989bb73e6d3383b3c4024e6e7
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104947"
---
# <a name="how-to-build-a-multifile-assembly"></a>Procedura: Creare un assembly su più file

In questo articolo viene illustrato come creare un assembly su più file e viene visualizzato il codice che illustra ogni passaggio della procedura.

> [!NOTE]
> L'IDE di Visual Studio per C# e Visual Basic può essere utilizzato esclusivamente per creare assembly su singolo file. Per creare assembly su più file, è necessario utilizzare i compilatori della riga di comando o Visual Studio con Visual C++. Gli assembly su più file sono supportati solo da .NET Framework.

## <a name="create-a-multifile-assembly"></a>Creare un assembly su più file

1. Compilare in moduli di codice tutti i file contenenti spazi dei nomi a cui fanno riferimento altri moduli dell'assembly. L'estensione predefinita per i moduli di codice è *. netmodule*.

   Si supponga, ad esempio, che il file `Stringer` abbia uno spazio dei nomi denominato `myStringer`, che include una classe denominata `Stringer`. Nella classe `Stringer` è disponibile un metodo denominato `StringerMethod`, che consente di scrivere una singola riga nella console.

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. Per compilare il codice, utilizzare il comando seguente:

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   Specificando il parametro *module* con l'opzione del compilatore **/t:** si indica che è necessario compilare il file come modulo anziché come assembly. Il compilatore produce un modulo denominato *Stringer. netmodule*, che può essere aggiunto a un assembly.

3. Compilare tutti gli altri moduli, utilizzando le opzioni di compilatore necessarie per indicare gli altri moduli a cui si fa riferimento nel codice. Questo passaggio usa l'opzione del compilatore **/addmodule**.

   Nell'esempio seguente, un modulo di codice denominato *client* dispone di un metodo del punto di ingresso `Main` che fa riferimento a un metodo nel modulo *Stringer.dll* creato nel passaggio 1.

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. Per compilare il codice, utilizzare il comando seguente:

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   Specificare l'opzione **/t:module** poiché il modulo verrà aggiunto a un assembly in un passaggio successivo. Specificare l'opzione **/addmodule** perché il codice nel *client* fa riferimento a uno spazio dei nomi creato dal codice in *Stringer. netmodule*. Il compilatore produce un modulo denominato *client. netmodule* che contiene un riferimento a un altro modulo, *Stringer.* netmodule.

   > [!NOTE]
   > Nei compilatori di C# e di Visual Basic viene supportata la creazione diretta di assembly su più file utilizzando le due diverse sintassi descritte di seguito.
   >
   > Un assembly su due file viene creato da due compilazioni:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > Un assembly su due file viene creato da una compilazione:
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. Usare [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) per creare il file di output contenente il manifesto dell'assembly. In questo file sono contenute informazioni di riferimento per tutti i moduli o le risorse che fanno parte dell'assembly.

    Al prompt dei comandi digitare il comando seguente:

    **al** \<*module name*> \<*module name*>... **/Main:** \<*method name*> **/out:** \<*file name*> **/target:**\<*assembly file type*>

    In questo comando gli argomenti *nome modulo* specificano il nome di ogni modulo da includere nell'assembly. L'opzione **/main:** specifica il nome del metodo che corrisponde al punto di ingresso dell'assembly. L'opzione **/out:** specifica il nome del file di output che contiene i metadati dell'assembly. L'opzione **/target:** specifica che l'assembly è un file eseguibile dell'applicazione console (*exe*), un file eseguibile di Windows (con*estensione win*) o un file di libreria (con*estensione LIB*).

    Nell'esempio seguente *Al.exe* crea un assembly che è un eseguibile dell'applicazione console chiamato *myAssembly.exe*. L'applicazione è costituita da due moduli denominati *client. netmodule* e *Stringer. netmodule*e il file eseguibile denominato *myAssembly.exe*, che contiene solo i metadati dell'assembly. Il punto di ingresso dell'assembly è il `Main` metodo nella classe `MainClientApp` , disponibile in *Client.dll*.

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    È possibile usare [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) per esaminare i contenuti di un assembly o determinare se un file è un assembly o un modulo.

## <a name="see-also"></a>Vedere anche

- [Creare assembly](../../standard/assembly/create.md)
- [Procedura: visualizzare il contenuto dell'assembly](../../standard/assembly/view-contents.md)
- [Come il runtime individua gli assembly](../deployment/how-the-runtime-locates-assemblies.md)
- [Assembly su più file](multifile-assemblies.md)
