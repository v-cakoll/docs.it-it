---
title: 'Esempio: Risoluzione dei problemi di programmazione dinamica'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 25a384fa2465be6f4e523410e69aba6813e5c22d
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="example-troubleshooting-dynamic-programming"></a>Esempio: Risoluzione dei problemi di programmazione dinamica
> [!NOTE]
>  In questo argomento si fa riferimento a .NET Native Developer Preview, ovvero la versione preliminare del software, che è possibile scaricare dal [sito Web di Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=394611) (è necessaria la registrazione).  
  
 Non tutti gli errori di ricerca di metadati nelle applicazioni sviluppate usando la catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)] generano un'eccezione.  Alcuni possono manifestarsi in maniera imprevista in un'applicazione.  Nell'esempio seguente viene illustrata una violazione di accesso causata da riferimento a un oggetto null:  
  
```  
Access violation - code c0000005 (first chance)  
App!$3_App::Core::Util::NavigationArgs.Setup  
App!$3_App::Core::Util::NavigationArgs..ctor  
App!$0_App::Gibbon::Util::DesktopNavigationArgs..ctor  
App!$0_App::ViewModels::DesktopAppVM.NavigateToPage  
App!$3_App::Core::ViewModels::AppViewModel.NavigateToFirstPage  
App!$3_App::Core::ViewModels::AppViewModel::<HandleLaunch>d__a.MoveNext  
App!$43_System::Runtime::CompilerServices::AsyncMethodBuilderCore.CallMoveNext  
App!System::Action.InvokeClosedStaticThunk  
App!System::Action.Invoke  
App!$43_System::Threading::Tasks::AwaitTaskContinuation.InvokeAction  
App!$43_System::Threading::SendOrPostCallback.InvokeOpenStaticThunk  
[snip]  
```  
  
 Si proverà a risolvere questa eccezione usando l'approccio in tre passaggi descritto nella sezione dedicata alla risoluzione manuale dei metadati mancanti di [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md) (Introduzione).  
  
## <a name="what-was-the-app-doing"></a>Che cosa stava eseguendo l'app?  
 La prima cosa da notare è il sistema di parole chiave `async` alla base dello stack.  Determinare cosa stesse facendo davvero l'applicazione in un metodo `async` può risultare problematico, perché lo stack ha perso il contesto di chiamata di origine e ha eseguito il codice `async` su un thread diverso. Tuttavia, è possibile dedurre che l'applicazione sta provando a caricare la prima pagina.  Nell'implementazione di `NavigationArgs.Setup`, il codice seguente ha causato la violazione di accesso:  
  
```  
AppViewModel.Current.LayoutVM.PageMap  
```  
  
 In questo caso, la proprietà `LayoutVM` su `AppViewModel.Current` era **null**.  Un'assenza di metadati ha causato una lieve differenza di comportamento e comportato l'annullamento dell'inizializzazione di una proprietà invece della relativa impostazione, come previsto dall'applicazione.  L'impostazione di un punto di interruzione nel codice dove `LayoutVM` avrebbe dovuto essere inizializzato potrebbe aiutare a fare chiarezza sulla situazione.  Tuttavia, notare che il tipo di `LayoutVM` è `App.Core.ViewModels.Layout.LayoutApplicationVM`.  L'unica direttiva di metadati presente finora nel file rd.xml è:  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 Un probabile candidato per l'errore è che i metadati sono assenti in `App.Core.ViewModels.Layout.LayoutApplicationVM` perché si trova in uno spazio dei nomi differente.  
  
 In questo caso, l'aggiunta di una direttiva di runtime per `App.Core.ViewModels` ha risolto il problema. La causa radice è stata una chiamata API al metodo <xref:System.Type.GetType%28System.String%29?displayProperty=fullName> che ha restituito **null** e l'applicazione ha automaticamente ignorato il problema fino a quando non si è verificato un arresto anomalo del sistema.  
  
 Nella programmazione dinamica, una buona norma quando si usano le API di reflection sotto [!INCLUDE[net_native](../../../includes/net-native-md.md)] consiste nell'usare gli overload di <xref:System.Type.GetType%2A?displayProperty=fullName> che generano un'eccezione all'errore.  
  
## <a name="is-this-an-isolated-case"></a>Si tratta di un caso isolato?  
 Quando si usa `App.Core.ViewModels` potrebbero insorgere altri problemi.  È necessario decidere se vale la pena identificare e correggere ogni eccezione dei metadati mancanti, oppure risparmiare tempo e aggiungere le direttive per una classe di tipi maggiore.  In questo caso, l'aggiunta dei metadati `dynamic` per `App.Core.ViewModels` potrebbe essere l'approccio migliore se l'aumento delle dimensioni del file binario di output risultante non è un problema.  
  
## <a name="could-the-code-be-rewritten"></a>È possibile riscrivere il codice?  
 Se l'app aveva usato `typeof(LayoutApplicationVM)` invece di `Type.GetType("LayoutApplicationVM")`, la catena di strumenti potrebbe aver preservato i metadati di `browse`.  I metadati `invoke` tuttavia non sarebbero stati comunque creati e ciò avrebbe prodotto un'eccezione [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) durante la creazione dell'istanza del tipo. Per prevenire l'eccezione, sarebbe comunque necessario aggiungere una direttiva di runtime per lo spazio dei nomi o per il tipo che specifica i criteri `dynamic`. Per informazioni sulle direttive di runtime, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md)   
 [Example: Handling Exceptions When Binding Data](../../../docs/framework/net-native/example-handling-exceptions-when-binding-data.md) (Esempio: Gestione delle eccezioni al momento del data binding)

