---
title: Tipi di isolamento
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: d85625b99603c0bd81346cf2076b8efe0e1bba42
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523879"
---
# <a name="types-of-isolation"></a>Tipi di isolamento
L'accesso allo spazio di memorizzazione isolato è sempre limitato all'utente che l'ha creata. Per implementare questo tipo di isolamento, Common Language Runtime usa la stessa nozione di identità utente riconosciuta dal sistema operativo, ovvero l'identità associata al processo in cui è in esecuzione il codice quando viene aperto lo spazio di memorizzazione. Sebbene sia un'identità utente autenticata, è possibile che con la rappresentazione l'identità dell'utente corrente venga modificata dinamicamente.  
  
 L'accesso allo spazio di memorizzazione isolato viene limitato anche in base all'identità associata all'assembly e al dominio dell'applicazione oppure solo all'assembly. Il runtime ottiene queste identità nei modi seguenti:  
  
- L'identità del dominio rappresenta l'evidenza dell'applicazione, che nel caso di un'applicazione Web può coincidere con l'URL completo. Per il codice su shell, l'identità del dominio può essere basata sul percorso di directory dell'applicazione. Se ad esempio il file eseguibile viene eseguito dal percorso C:\Office\MyApp.exe, l'identità del dominio sarà C:\Office\MyApp.exe.  
  
- L'identità dell'assembly è l'evidenza dell'assembly. Può derivare da una firma digitale crittografica, che può corrispondere al [nome sicuro](../assembly/strong-named.md) dell'assembly, all'editore dell'assembly oppure all'identità del relativo URL. Se un assembly dispone sia di un'identità fornita dal nome sicuro sia di un'identità fornita dall'editore, verrà usata quella fornita dall'editore. Se l'assembly proviene da Internet e non è firmato, verrà usata invece l'identità dell'URL. Per altre informazioni sugli assembly e sui nomi sicuri, vedere [Programmazione con gli assembly](/dotnet/standard/assembly/index).  
  
- Gli spazi di memorizzazione roaming si spostano con gli utenti che dispongono di un profilo di utente roaming. I file vengono scritti in una directory di rete e scaricati su qualsiasi computer a cui l'utente accede. Per altre informazioni sui profili di utente roaming, vedere <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Roaming?displayProperty=nameWithType>.  
  
 Combinando i concetti di identità di utente, dominio e assembly, lo spazio di memorizzazione isolato può isolare i dati nei modi seguenti, ciascuno dei quali presenta specifici scenari di utilizzo:  
  
- [Isolamento per utente e assemblaggio](#UserAssembly)  
  
- [Isolamento per utente, dominio e assembly](#UserDomainAssembly)  
  
 Ognuno di questi isolamenti può essere combinato con un profilo di utente roaming. Per altre informazioni, vedere la sezione [Spazio di memorizzazione isolato e roaming](#Roaming).  
  
 La figura seguente illustra come vengono isolati gli archivi in ambiti diversi:  
  
 ![Diagramma che illustra l'isolamento in base a utente e assembly.](./media/types-of-isolation/isolated-storage-types.gif)  
  
 Si osservi che, fatta eccezione per gli spazi di memorizzazione roaming, lo spazio di memorizzazione isolato viene sempre isolato implicitamente in base al computer, poiché usa le funzioni di memorizzazione locali del computer in uso.  
  
> [!IMPORTANT]
> L'archiviazione isolata non è disponibile per le app di Windows 8.x Store. Al contrario, usare le classi di dati dell'applicazione negli spazi dei nomi `Windows.Storage` inclusi nell'API di Windows Runtime per archiviare dati e file locali. Per altre informazioni, vedere [Dati dell'applicazione](https://docs.microsoft.com/previous-versions/windows/apps/hh464917(v=win.10)) nel Centro per sviluppatori Windows.  
  
<a name="UserAssembly"></a>
## <a name="isolation-by-user-and-assembly"></a>Isolamento in base all'utente e all'assembly  
 L'isolamento in base all'utente e all'assembly è indicato quando si vuole che l'assembly che usa l'archivio dati sia accessibile da qualsiasi dominio dell'applicazione. In genere, in questa situazione, lo spazio di memorizzazione isolato viene usato per memorizzare dati che riguardano più applicazioni e non una singola applicazione, come il nome utente e informazioni sulla licenza. Per poter accedere a uno spazio di memorizzazione isolato in base all'utente e all'assembly, è necessario che il codice sia considerato attendibile per il trasferimento di informazioni tra applicazioni diverse. In genere, l'isolamento in base all'utente e all'assembly è consentito in reti Intranet, ma non in Internet. Chiamando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A?displayProperty=nameWithType> e passando un utente e un assembly <xref:System.IO.IsolatedStorage.IsolatedStorageScope>, viene restituito uno spazio di memorizzazione con questo tipo di isolamento.  
  
 L'esempio di codice seguente recupera uno spazio di memorizzazione isolato in base all'utente e all'assembly. È possibile accedere allo spazio di memorizzazione tramite l'oggetto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#17)]
 [!code-csharp[Conceptual.IsolatedStorage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#17)]
 [!code-vb[Conceptual.IsolatedStorage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#17)]  
  
 Per un esempio in cui vengono usati i parametri di evidenza, vedere <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%28System.IO.IsolatedStorage.IsolatedStorageScope%2CSystem.Security.Policy.Evidence%2CSystem.Type%2CSystem.Security.Policy.Evidence%2CSystem.Type%29>.  
  
 Come alternativa è disponibile il metodo <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, come illustrato nell'esempio di codice seguente. Questa alternativa, tuttavia, non può essere usata per aprire spazi di memorizzazione in cui può essere abilitato il roaming. In questi casi, usare <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source11.cpp#18)]
 [!code-csharp[Conceptual.IsolatedStorage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source11.cs#18)]
 [!code-vb[Conceptual.IsolatedStorage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source11.vb#18)]  
  
<a name="UserDomainAssembly"></a>
## <a name="isolation-by-user-domain-and-assembly"></a>Isolamento in base all'utente, al dominio e all'assembly  
 Se un'applicazione usa un assembly di terze parti che richiede un archivio dati privato, è possibile usare lo spazio di memorizzazione isolato per memorizzare i dati privati. L'isolamento in base all'utente, al dominio e all'assembly garantisce che ai dati possa accedere solo il codice di un determinato assembly, solo quando l'assembly viene usato dall'applicazione che era in esecuzione nel momento in cui l'assembly ha creato lo spazio di memorizzazione e solo quando l'applicazione viene eseguita dall'utente per il quale è stato creato lo spazio di memorizzazione. L'isolamento in base all'utente, al dominio e all'assembly impedisce che l'assembly di terze parti passi i dati ad altre applicazioni. È opportuno scegliere questo tipo di isolamento se si è certi di voler usare lo spazio di memorizzazione isolato, ma non si è sicuri del tipo di isolamento da usare. Chiamando il metodo statico <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> di <xref:System.IO.IsolatedStorage.IsolatedStorageFile> e passando un utente, un dominio e un assembly, <xref:System.IO.IsolatedStorage.IsolatedStorageScope> restituisce lo spazio di memorizzazione con questo tipo di isolamento.  
  
 Nell'esempio di codice seguente viene recuperato uno spazio di memorizzazione isolato in base all'utente, al dominio e all'assembly. È possibile accedere allo spazio di memorizzazione tramite l'oggetto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#14)]
 [!code-csharp[Conceptual.IsolatedStorage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#14)]
 [!code-vb[Conceptual.IsolatedStorage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#14)]  
  
 Come alternativa è disponibile un altro metodo, come illustrato nell'esempio di codice seguente. Questa alternativa, tuttavia, non può essere usata per aprire spazi di memorizzazione in cui può essere abilitato il roaming. In questi casi, usare <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 [!code-cpp[Conceptual.IsolatedStorage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source10.cpp#15)]
 [!code-csharp[Conceptual.IsolatedStorage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source10.cs#15)]
 [!code-vb[Conceptual.IsolatedStorage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source10.vb#15)]  
  
<a name="Roaming"></a>
## <a name="isolated-storage-and-roaming"></a>Spazio di memorizzazione isolato e roaming  
 I profili utente mobili sono una funzionalità di Windows che consente a un utente di impostare un'identità in una rete e usarla per accedere a qualsiasi computer di rete, conservando tutte le impostazioni personalizzate. Un assembly che usa lo spazio di memorizzazione isolato può specificare che lo spazio di memorizzazione isolato dell'utente si sposti con il profilo utente mobile. Il roaming può essere usato con l'isolamento in base all'utente e all'assembly oppure con l'isolamento in base all'utente, al dominio e all'assembly. Se non viene usato un ambito di roaming, gli spazi di memorizzazione non si spostano neppure se viene usato un profilo utente mobile.  
  
 Nell'esempio di codice seguente viene recuperato uno spazio di memorizzazione di roaming isolato in base all'utente e all'assembly. È possibile accedere allo spazio di memorizzazione tramite l'oggetto `isoFile`.  
  
 [!code-cpp[Conceptual.IsolatedStorage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#11)]
 [!code-csharp[Conceptual.IsolatedStorage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#11)]
 [!code-vb[Conceptual.IsolatedStorage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#11)]  
  
 È possibile aggiungere un ambito di dominio per creare uno spazio di memorizzazione di roaming isolato in base all'utente, al dominio e all'applicazione. Nell'esempio di codice seguente viene illustrata questa possibilità.  
  
 [!code-cpp[Conceptual.IsolatedStorage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source9.cpp#12)]
 [!code-csharp[Conceptual.IsolatedStorage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source9.cs#12)]
 [!code-vb[Conceptual.IsolatedStorage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source9.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.IsolatedStorage.IsolatedStorageScope>
- [Archiviazione isolata](../../../docs/standard/io/isolated-storage.md)
