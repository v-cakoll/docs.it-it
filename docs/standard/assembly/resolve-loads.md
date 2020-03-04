---
title: Risolvere i caricamenti di assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: d6314fae266505fbb4410aaaa351973070ab3811
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156439"
---
# <a name="resolve-assembly-loads"></a>Risolvere i caricamenti di assembly
.NET fornisce l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per le applicazioni che richiedono un maggiore controllo sul caricamento degli assembly. Con questo evento, l'applicazione può caricare un assembly nel contesto di caricamento dall'esterno di percorsi di sondaggio normale, selezionare la versione di assembly da caricare, creare e restituire un assembly dinamico e così via. Questo argomento illustra il materiale sussidiario per la gestione dell'evento <xref:System.AppDomain.AssemblyResolve>.  
  
> [!NOTE]
> Per la risoluzione di caricamenti di assembly nel solo contesto di reflection, usare invece l'evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=nameWithType>.  
  
## <a name="how-the-assemblyresolve-event-works"></a>Funzionamento dell'evento AssemblyResolve  
 Quando si registra un gestore per l'evento <xref:System.AppDomain.AssemblyResolve>, il gestore viene richiamato ogni volta che il runtime non riesce ad associarlo a un assembly in base al nome. Ad esempio, la chiamata dei metodi seguenti dal codice utente può causare l'evento <xref:System.AppDomain.AssemblyResolve>:  
  
- Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, il cui primo argomento è una stringa che rappresenta il nome visualizzato dell'assembly da caricare (ovvero, la stringa restituita dalla proprietà <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>).  
  
- Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, il cui primo argomento è un oggetto <xref:System.Reflection.AssemblyName> che identifica l'assembly da caricare.  
  
- Un overload del metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>.  
  
- Un overload del metodo <xref:System.AppDomain.CreateInstance%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType> che crea un'istanza di un oggetto in un altro dominio di applicazioni.  
  
### <a name="what-the-event-handler-does"></a>Funzione del gestore eventi  
 Il gestore per l'evento <xref:System.AppDomain.AssemblyResolve> riceve il nome visualizzato dell'assembly da caricare nella proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType>. Se il gestore non riconosce il nome dell'assembly, restituisce `null` (C#), `Nothing` (Visual Basic) o `nullptr` (oggetto visivo C++).  
  
 Se il gestore riconosce il nome dell'assembly, può caricare e restituire un assembly che soddisfi la richiesta. Nell'elenco seguente vengono illustrati alcuni scenari di esempio.  
  
- Se il gestore conosce il percorso di una versione dell'assembly, può caricare l'assembly usando il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=nameWithType> e può restituire l'assembly caricato, se ha esito positivo.  
  
- Se il gestore ha accesso a un database di assembly archiviati come matrici di byte, può caricare una matrice di byte usando uno degli overload del metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> che accetta una matrice di byte.  
  
- Il gestore può generare e restituire un assembly dinamico.  
  
> [!NOTE]
> Il gestore deve caricare l'assembly nel contesto di caricamento di provenienza, nel contesto di caricamento o in nessun contesto. Se il gestore carica l'assembly nel contesto di reflection solo usando il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>, il tentativo di caricamento che ha generato l'evento <xref:System.AppDomain.AssemblyResolve> ha esito negativo.  
  
 È compito del gestore eventi restituire un assembly appropriato. Il gestore può analizzare il nome visualizzato dell'assembly richiesto passando il valore della proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=nameWithType> al costruttore <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>. A partire da .NET Framework 4, il gestore può usare la proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> per determinare se la richiesta corrente è una dipendenza di un altro assembly. Questa informazione può aiutare a identificare un assembly che soddisferà la dipendenza.  
  
 Il gestore eventi può restituire una versione diversa dell'assembly rispetto alla versione richiesta.  
  
 Nella maggior parte dei casi, l'assembly restituito dal gestore viene visualizzato nel contesto di caricamento, indipendentemente dal contesto in cui lo carica il gestore. Ad esempio, se il gestore usa il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> per caricare un assembly nel contesto di caricamento di provenienza, l'assembly viene visualizzato nel contesto di caricamento quando viene restituito dal gestore. Tuttavia, nel caso seguente l'assembly viene visualizzato senza contesto quando viene restituito dal gestore:  
  
- Il gestore carica un assembly senza contesto.  
  
- La proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType> non è Null.  
  
- L'assembly richiedente (vale a dire l'assembly restituito dalla proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=nameWithType>) è stato caricato senza contesto.  
  
 Per informazioni sui contesti, vedere l'overload del metodo <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=nameWithType>.  
  
 È possibile caricare più versioni dello stesso assembly nello stesso dominio di applicazioni. Questa pratica non è consigliata, perché può causare problemi di assegnazione del tipo. Vedere le [procedure consigliate per il caricamento di assembly](../../framework/deployment/best-practices-for-assembly-loading.md).  
  
### <a name="what-the-event-handler-should-not-do"></a>Cosa non deve fare il gestore eventi  
La regola principale nella gestione di eventi <xref:System.AppDomain.AssemblyResolve> è che non si deve provare a restituire un assembly non riconosciuta. Quando si scrive il gestore, è necessario conoscere gli assembly che potrebbero causare la generazione dell'evento. Il gestore deve restituire Null per gli altri assembly.  

> [!IMPORTANT]
> A partire da .NET Framework 4, l'evento <xref:System.AppDomain.AssemblyResolve> viene generato per gli assembly satellite. Questa modifica interessa un gestore eventi scritto per una versione precedente di .NET Framework, se il gestore proverà a risolvere tutte le richieste di caricamento di assembly. I gestori di eventi, che ignorano gli assembly non riconosciuti, non sono interessati da questa modifica. Infatti restituiscono Null e seguono i normali meccanismi di fallback.  

Quando si carica un assembly, il gestore eventi non deve usare nessun overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> che può causare la generazione dell'evento <xref:System.AppDomain.AssemblyResolve> in modo ricorsivo, poiché questo può causare un overflow dello stack. Vedere l'elenco fornito in precedenza in questo argomento. Ciò si verifica anche se si fornisce la gestione delle eccezioni per la richiesta di caricamento, perché non viene generata alcuna eccezione fino a quando non vengono restituiti tutti i gestori eventi. Di conseguenza, il codice seguente causa un overflow dello stack se `MyAssembly` non viene trovato:  

```cpp
using namespace System;
using namespace System::Reflection;

ref class Example
{
internal:
    static Assembly^ MyHandler(Object^ source, ResolveEventArgs^ e)
    {
        Console::WriteLine("Resolving {0}", e->Name);
        return Assembly::Load(e->Name);
    }
};

void main()
{
    AppDomain^ ad = AppDomain::CreateDomain("Test");
    ad->AssemblyResolve += gcnew ResolveEventHandler(&Example::MyHandler);

    try
    {
        Object^ obj = ad->CreateInstanceAndUnwrap(
            "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
            "MyType");
    }
    catch (Exception^ ex)
    {
        Console::WriteLine(ex->Message);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```csharp
using System;
using System.Reflection;

class BadExample
{
    static void Main()
    {
        AppDomain ad = AppDomain.CreateDomain("Test");
        ad.AssemblyResolve += MyHandler;

        try
        {
            object obj = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType");
        }
        catch (Exception ex)
        {
            Console.WriteLine(ex.Message);
        }
    }

    static Assembly MyHandler(object source, ResolveEventArgs e)
    {
        Console.WriteLine("Resolving {0}", e.Name);
        return Assembly.Load(e.Name);
    }
}

/* This example produces output similar to the following:

Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
...
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null

Process is terminated due to StackOverflowException.
 */
```

```vb
Imports System.Reflection

Class BadExample

    Shared Sub Main()

        Dim ad As AppDomain = AppDomain.CreateDomain("Test")
        AddHandler ad.AssemblyResolve, AddressOf MyHandler

        Try
            Dim obj As object = ad.CreateInstanceAndUnwrap(
                "MyAssembly, version=1.2.3.4, culture=neutral, publicKeyToken=null",
                "MyType")
        Catch ex As Exception
            Console.WriteLine(ex.Message)
        End Try
    End Sub

    Shared Function MyHandler(ByVal source As Object, _
                              ByVal e As ResolveEventArgs) As Assembly
        Console.WriteLine("Resolving {0}", e.Name)
        Return Assembly.Load(e.Name)
    End Function
End Class

' This example produces output similar to the following:
'
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'...
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'Resolving MyAssembly, Version=1.2.3.4, Culture=neutral, PublicKeyToken=null
'
'Process is terminated due to StackOverflowException.
```

## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per il caricamento di assembly](../../framework/deployment/best-practices-for-assembly-loading.md)
- [Usare i domini applicazione](../../framework/app-domains/use.md)
