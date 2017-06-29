---
title: Risoluzione dei caricamenti di assembly | Microsoft Docs
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
- assemblies [.NET Framework], resolving loads
- application domains, loading assemblies
- resolving assembly loads
- assemblies [.NET Framework], loading
- application domains, resolving assembly loads
ms.assetid: 5099e549-f4fd-49fb-a290-549edd456c6a
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 71dfb65710a536c5cc470681285073a21da4c770
ms.contentlocale: it-it
ms.lasthandoff: 06/02/2017

---
# <a name="resolving-assembly-loads"></a>risoluzione caricamenti assembly
.NET Framework offre l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> per le applicazioni che richiedono un maggiore controllo sul caricamento di assembly. Con questo evento, l'applicazione può caricare un assembly nel contesto di caricamento dall'esterno di percorsi di sondaggio normale, selezionare la versione di assembly da caricare, creare e restituire un assembly dinamico e così via. Questo argomento illustra il materiale sussidiario per la gestione dell'evento <xref:System.AppDomain.AssemblyResolve>.  
  
> [!NOTE]
>  Per la risoluzione di caricamenti di assembly nel solo contesto di reflection, usare invece l'evento <xref:System.AppDomain.ReflectionOnlyAssemblyResolve?displayProperty=fullName>.  
  
## <a name="how-the-assemblyresolve-event-works"></a>Funzionamento dell'evento AssemblyResolve  
 Quando si registra un gestore per l'evento <xref:System.AppDomain.AssemblyResolve>, il gestore viene richiamato ogni volta che il runtime non riesce ad associarlo a un assembly in base al nome. Ad esempio, la chiamata dei metodi seguenti dal codice utente può causare l'evento <xref:System.AppDomain.AssemblyResolve>:  
  
-   Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>, il cui primo argomento è una stringa che rappresenta il nome visualizzato dell'assembly da caricare (ovvero, la stringa restituita dalla proprietà <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>).  
  
-   Un overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>, il cui primo argomento è un oggetto <xref:System.Reflection.AssemblyName> che identifica l'assembly da caricare.  
  
-   Un overload del metodo <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>.  
  
-   Un overload del metodo <xref:System.AppDomain.CreateInstance%2A?displayProperty=fullName> o <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName> che crea un'istanza di un oggetto in un altro dominio di applicazioni.  
  
### <a name="what-the-event-handler-does"></a>Funzionamento del gestore eventi  
 Il gestore per l'evento <xref:System.AppDomain.AssemblyResolve> riceve il nome visualizzato dell'assembly da caricare nella proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName>. Se il gestore non riconosce il nome dell'assembly, viene restituito Null (`Nothing` in Visual Basic, `nullptr` in Visual C++).  
  
 Se il gestore riconosce il nome dell'assembly, può caricare e restituire un assembly che soddisfi la richiesta. Nell'elenco seguente vengono illustrati alcuni scenari di esempio.  
  
-   Se il gestore conosce il percorso di una versione dell'assembly, può caricare l'assembly usando il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName> e può restituire l'assembly caricato, se ha esito positivo.  
  
-   Se il gestore ha accesso a un database di assembly archiviati come matrici di byte, può caricare una matrice di byte usando uno degli overload del metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> che accetta una matrice di byte.  
  
-   Il gestore può generare e restituire un assembly dinamico.  
  
> [!NOTE]
>  Il gestore deve caricare l'assembly nel contesto di caricamento di provenienza, nel contesto di caricamento o in nessun contesto. Se il gestore carica l'assembly nel contesto di reflection solo usando il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=fullName>, il tentativo di caricamento che ha generato l'evento <xref:System.AppDomain.AssemblyResolve> ha esito negativo.  
  
 È compito del gestore eventi restituire un assembly appropriato. Il gestore può analizzare il nome visualizzato dell'assembly richiesto passando il valore della proprietà <xref:System.ResolveEventArgs.Name%2A?displayProperty=fullName> al costruttore <xref:System.Reflection.AssemblyName.%23ctor%28System.String%29>. A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], il gestore può usare la proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> per determinare se la richiesta corrente è una dipendenza di un altro assembly. Questa informazione può aiutare a identificare un assembly che soddisferà la dipendenza.  
  
 Il gestore eventi può restituire una versione diversa dell'assembly rispetto alla versione richiesta.  
  
 Nella maggior parte dei casi, l'assembly restituito dal gestore viene visualizzato nel contesto di caricamento, indipendentemente dal contesto in cui lo carica il gestore. Ad esempio, se il gestore usa il metodo <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> per caricare un assembly nel contesto di caricamento di provenienza, l'assembly viene visualizzato nel contesto di caricamento quando viene restituito dal gestore. Tuttavia, nel caso seguente l'assembly viene visualizzato senza contesto quando viene restituito dal gestore:  
  
-   Il gestore carica un assembly senza contesto.  
  
-   La proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName> non è Null.  
  
-   L'assembly richiedente (vale a dire l'assembly restituito dalla proprietà <xref:System.ResolveEventArgs.RequestingAssembly%2A?displayProperty=fullName>) è stato caricato senza contesto.  
  
 Per informazioni sui contesti, vedere l'overload del metodo <xref:System.Reflection.Assembly.LoadFrom%28System.String%29?displayProperty=fullName>.  
  
 È possibile caricare più versioni dello stesso assembly nello stesso dominio di applicazioni. Questa pratica non è consigliata, perché può causare problemi di assegnazione del tipo. Vedere [Best Practices for Assembly Loading](../../../docs/framework/deployment/best-practices-for-assembly-loading.md) (Procedure consigliate per il caricamento di assembly).  
  
### <a name="what-the-event-handler-should-not-do"></a>Operazioni che il gestore eventi non deve eseguire  
 La regola principale nella gestione di eventi <xref:System.AppDomain.AssemblyResolve> è che non si deve provare a restituire un assembly non riconosciuta. Quando si scrive il gestore, è necessario conoscere gli assembly che potrebbero causare la generazione dell'evento. Il gestore deve restituire Null per gli altri assembly.  
  
> [!IMPORTANT]
>  A partire da [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], l'evento <xref:System.AppDomain.AssemblyResolve> viene generato per gli assembly satellite. Questa modifica interessa un gestore eventi scritto per una versione precedente di .NET Framework, se il gestore proverà a risolvere tutte le richieste di caricamento di assembly. I gestori di eventi, che ignorano gli assembly non riconosciuti, non sono interessati da questa modifica. Infatti restituiscono Null e seguono i normali meccanismi di fallback.  
  
 Quando si carica un assembly, il gestore eventi non deve usare nessun overload del metodo <xref:System.AppDomain.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> che può causare la generazione dell'evento <xref:System.AppDomain.AssemblyResolve> in modo ricorsivo, poiché questo può causare un overflow dello stack. Vedere l'elenco illustrato in precedenza in questo argomento. Ciò avviene anche se si specifica una gestione di eccezioni per la richiesta di caricamento, perché non viene generata alcuna eccezione fino a quando non sono restituiti tutti i gestori eventi. Di conseguenza, il codice seguente causa un overflow dello stack se `MyAssembly` non viene trovato:  
  
 [!code-cpp[AssemblyResolveRecursive#1](../../../samples/snippets/cpp/VS_Snippets_CLR/assemblyresolverecursive/cpp/example.cpp#1)] [!code-csharp[AssemblyResolveRecursive#1](../../../samples/snippets/csharp/VS_Snippets_CLR/assemblyresolverecursive/cs/example.cs#1)] [!code-vb[AssemblyResolveRecursive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/assemblyresolverecursive/vb/example.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Best Practices for Assembly Loading](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)  (Procedure consigliate per il caricamento di assembly)  
 [Uso dei domini dell'applicazione](../../../docs/framework/app-domains/use.md)
