---
title: 'Procedura: trovare il nome completo di un assembly'
description: Questo articolo illustra come ottenere il nome completo di un assembly .NET Framework o di un assembly .NET Core.
ms.date: 08/20/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 346d50dc7f279ce46c9803ad60479d3111739c25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378941"
---
# <a name="how-to-find-an-assemblys-fully-qualified-name"></a>Procedura: trovare il nome completo di un assembly

Per individuare il nome completo di un assembly .NET Framework nella Global Assembly Cache, usare lo strumento Global Assembly Cache ([gacutil. exe](../../framework/tools/gacutil-exe-gac-tool.md)). Vedere [procedura: visualizzare il contenuto del Global assembly cache](../../framework/app-domains/how-to-view-the-contents-of-the-gac.md).

Per gli assembly .NET Core e per gli assembly .NET Framework che non sono inclusi nella Global Assembly Cache, è possibile ottenere il nome completo dell'assembly in diversi modi:

- È possibile utilizzare il codice per restituire le informazioni alla console o a una variabile oppure è possibile utilizzare [Ildasm. exe (DISASSEMBLER il)](../../framework/tools/ildasm-exe-il-disassembler.md) per esaminare i metadati dell'assembly, che contengono il nome completo.

- Se l'assembly è già stato caricato dall'applicazione, è possibile recuperare il valore della proprietà <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> per ottenere il nome completo. È possibile utilizzare la <xref:System.Type.Assembly> proprietà di un <xref:System.Type> oggetto definito in tale assembly per recuperare un riferimento all' <xref:System.Reflection.Assembly> oggetto. Nell'esempio viene illustrata una situazione di questo tipo.

- Se si conosce il percorso di file system dell'assembly, è possibile chiamare il `static` Metodo (C#) o `Shared` (Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> per ottenere il nome completo dell'assembly. Di seguito è riportato un esempio semplice.

  ```csharp
  using System;
  using System.Reflection;

  public class Example
  {
     public static void Main()
     {
        Console.WriteLine(AssemblyName.GetAssemblyName(@".\UtilityLibrary.dll"));
     }
  }
  // The example displays output like the following:
  //   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

  ```vb
  Imports System.Reflection

  Public Module Example
     Public Sub Main
        Console.WriteLine(AssemblyName.GetAssemblyName(".\UtilityLibrary.dll"))
     End Sub
  End Module
  ' The example displays output like the following:
  '   UtilityLibrary, Version=1.1.0.0, Culture=neutral, PublicKeyToken=null
  ```

- È possibile usare [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) per esaminare i metadati dell'assembly che contengono il nome completo.

Per ulteriori informazioni sull'impostazione degli attributi dell'assembly, ad esempio la versione, la lingua e il nome dell'assembly, vedere [impostare gli attributi](set-attributes.md)dell'assembly. Per altre informazioni su come assegnare un nome sicuro a un assembly, vedere [creare e usare assembly con nome sicuro](create-use-strong-named.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come visualizzare il nome completo di un assembly contenente una classe specificata nella console. Usa la <xref:System.Type.Assembly?displayProperty=nameWithType> proprietà per recuperare un riferimento a un assembly da un tipo definito in tale assembly.

```cpp
#using <System.dll>
#using <System.Data.dll>

using namespace System;
using namespace System::Reflection;

ref class asmname
{
public:
    static void Main()
    {
        Type^ t = System::Data::DataSet::typeid;
        String^ s = t->Assembly->FullName->ToString();
        Console::WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
};

int main()
{
    asmname::Main();
}
```

```csharp
using System;
using System.Reflection;

class asmname
{
    public static void Main()
    {
        Type t = typeof(System.Data.DataSet);
        string s = t.Assembly.FullName.ToString();
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s);
    }
}
```

```vb
Imports System.Reflection

Class asmname
    Public Shared Sub Main()
        Dim t As Type = GetType(System.Data.DataSet)
        Dim s As String = t.Assembly.FullName.ToString()
        Console.WriteLine("The fully qualified assembly name " +
            "containing the specified class is {0}.", s)
    End Sub
End Class
```

## <a name="see-also"></a>Vedere anche

- [Nomi degli assembly](names.md)
- [Creare assembly](create.md)
- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
- [Assembly Cache globale](../../framework/app-domains/gac.md)
- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
