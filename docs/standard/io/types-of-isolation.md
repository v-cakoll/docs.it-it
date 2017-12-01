---
title: Tipi di isolamento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- storing data using isolated storage, accessing isolated storage
- storing data using isolated storage, isolation types
- authentication [.NET Framework], isolated storage
- assemblies [.NET Framework], identity
- isolated storage, accessing
- data storage using isolated storage, isolation types
- data storage using isolated storage, accessing isolated storage
- domain identity
- isolated storage, types
- user authentication, isolated storage
ms.assetid: 14812988-473f-44ae-b75f-fd5c2f21fb7b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6b07c090a381925f5330a820214126a121d3790b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-isolation"></a>Tipi di isolamento
Accesso all'archiviazione isolata è sempre limitato all'utente che lo ha creato. Per implementare questo tipo di isolamento, common language runtime utilizza la stessa nozione di identità dell'utente che il sistema operativo riconosce, che indica l'identità associata al processo in cui viene eseguito il codice quando l'archivio viene aperto. Questa identità è un'identità utente autenticato, ma la rappresentazione può causare l'identità dell'utente corrente per modificare in modo dinamico.  
  
 Accesso all'archiviazione isolata è inoltre limitato in base all'identità associate a dominio dell'applicazione e assembly o solo all'assembly. Il runtime Ottiene queste identità nei modi seguenti:  
  
-   Identità di dominio rappresenta la prova dell'applicazione, che, nel caso di un'applicazione web, potrebbe essere l'URL completo. Per il codice su shell, l'identità di dominio potrebbe essere basata sul percorso di directory dell'applicazione. Ad esempio, se il file eseguibile viene eseguito dal percorso C:\Office\MyApp.exe, l'identità del dominio sarà C:\Office\MyApp.exe.  
  
-   Identità dell'assembly è l'evidenza dell'assembly. Potrebbe derivare da una firma digitale crittografia, che può essere l'assembly [con nome sicuro](../../../docs/framework/app-domains/strong-named-assemblies.md), l'autore del software dell'assembly o la propria identità di URL. Se un assembly ha un nome sicuro e dell'identità, viene utilizzata l'identità del server di pubblicazione del software. Se l'assembly proviene da Internet e non è firmato, viene utilizzata l'identità dell'URL. Per ulteriori informazioni sugli assembly e i nomi sicuri, vedere [programmazione con assembly](../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
-   Archivi roaming si spostano con un utente che dispone di un profilo utente mobile. I file vengono scritti in una directory di rete e vengono scaricati l'utente accede a qualsiasi computer. Per ulteriori informazioni sui profili utente mobili, vedere <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Combinando i concetti di utente, dominio e l'identità dell'assembly, spazio di memorizzazione isolato può isolare i dati nei modi seguenti, ognuno dei quali ha un proprio scenari di utilizzo:  
  
-   [Isolamento in base all'utente e all'assembly](#UserAssembly)  
  
-   [Isolamento in base all'utente, dominio e assembly](#UserDomainAssembly)  
  
 Uno di questi isolamento può essere combinato con un profilo utente mobile. Per ulteriori informazioni, vedere la sezione [spazio di memorizzazione isolato e Roaming](#Roaming).  
  
 Nella figura seguente viene illustrato come gli archivi vengono isolati in ambiti diversi.  
  
 ![Isolamento in base all'utente e all'assembly](../../../docs/standard/io/media/typesofisolation.gif "typesofisolation")  
Tipi di memorizzazione isolato  
  
 Si noti che, ad eccezione gli archivi roaming, spazio di memorizzazione isolato è sempre isolato in modo implicito dal computer perché utilizza le funzionalità di archiviazione locali per un determinato computer.  
  
> [!IMPORTANT]
>  Lo spazio di memorizzazione isolato non è disponibile per le applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Al contrario, utilizzare le classi di dati dell'applicazione negli spazi dei nomi `Windows.Storage` inclusi nell'API [!INCLUDE[wrt](../../../includes/wrt-md.md)] per archiviare dati e file locali. Per altre informazioni, vedere [Dati dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=229175) nel Centro per sviluppatori Windows.  
  
<a name="UserAssembly"></a>   
## <a name="isolation-by-user-and-assembly"></a>Isolamento in base all'utente e all'Assembly  
 Quando l'assembly che utilizza i dati archivio deve essere accessibile da qualsiasi dominio applicazione, l'isolamento utente e all'assembly è appropriato. In genere, in questo caso, l'archiviazione isolata viene utilizzata per archiviare i dati che riguardano più applicazioni e non sono correlati a un'applicazione specifica, ad esempio il nome dell'utente o le informazioni sulla licenza. Per accedere all'archiviazione isolata dall'utente e all'assembly, codice deve essere considerato attendibile per trasferire informazioni tra applicazioni. In genere, l'isolamento utente e all'assembly è consentito nelle reti Intranet, ma non su Internet. La chiamata al metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> metodo e passando un utente e un assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> restituisce un'archiviazione con questo tipo di isolamento.  
  
 Esempio di codice seguente recupera un archivio isolato in base a utente e all'assembly. L'archivio è possibile accedere tramite il `isoFile` oggetto.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Per un esempio che utilizza i parametri di prova, vedere <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Il <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> metodo è disponibile come collegamento, come illustrato nell'esempio di codice seguente. Questa scelta rapida non può essere utilizzata per aprire gli archivi idonei comuni. Utilizzare <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in tali casi.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>   
## <a name="isolation-by-user-domain-and-assembly"></a>Isolamento in base all'utente, dominio e Assembly  
 Se l'applicazione utilizza un assembly di terze parti che richiede un archivio dati privati, è possibile utilizzare l'archiviazione isolata per archiviare i dati privati. Isolamento in base all'utente, dominio e assembly garantisce che solo i dati, accessibile dal codice in un assembly specificato e solo quando l'assembly viene utilizzata dall'applicazione che era in esecuzione quando l'assembly creato nell'archivio e solo quando l'utente per cui è stato creato l'archivio viene eseguito il  applicazione. Isolamento in base all'utente, dominio e assembly mantiene l'assembly di terze parti dalla perdita di dati ad altre applicazioni. Questo tipo di isolamento deve essere la scelta predefinita, se si sa che si desidera utilizzare l'archiviazione isolata, ma non conoscono il tipo di isolamento da utilizzare. La chiamata al metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile> e passando un utente, dominio e assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope> restituisce un'archiviazione con questo tipo di isolamento.  
  
 Esempio di codice seguente recupera un archivio isolato dall'utente, dominio e assembly. L'archivio è possibile accedere tramite il `isoFile` oggetto.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Un altro metodo è disponibile come collegamento, come illustrato nell'esempio di codice seguente. Questa scelta rapida non può essere utilizzata per aprire gli archivi idonei comuni. Utilizzare <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> in tali casi.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>   
## <a name="isolated-storage-and-roaming"></a>Spazio di memorizzazione isolato e Roaming  
 I profili utente mobili sono una funzionalità di Windows che consente all'utente di impostare un'identità in una rete e utilizzare tale identità per l'accesso a qualsiasi computer della rete, conservando tutte le impostazioni personalizzate. È possibile specificare un assembly che utilizza spazio di memorizzazione isolato che è consigliabile spostare spazio di memorizzazione isolato dell'utente con profilo utente mobile. Roaming utilizzabile in combinazione con l'isolamento utente e all'assembly o con l'isolamento utente, dominio e all'assembly. Se non viene utilizzato un ambito comune, anche se viene utilizzato un profilo utente mobile non effettuerà il roaming archivi.  
  
 Esempio di codice seguente recupera un archivio roaming isolato dall'utente e all'assembly. L'archivio è possibile accedere tramite il `isoFile` oggetto.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 È possibile aggiungere un ambito di dominio per creare un archivio roaming isolato dall'utente, dominio e dell'applicazione. Esempio di codice seguente viene illustrato questo.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Spazio di memorizzazione isolato](../../../docs/standard/io/isolated-storage.md)
