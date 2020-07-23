---
title: Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente
description: Vedere come usare la memorizzazione nella cache in automazione interfaccia utente. Esaminare i passaggi per attivare una richiesta della cache, memorizzare nella cache le proprietà di AutomationElement e ottenere i modelli memorizzati nella cache.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 8dff9db77e39dc66a16b6a7b395c76a3c768d48e
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924487"
---
# <a name="use-caching-in-ui-automation"></a>Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questa sezione viene illustrato come implementare la memorizzazione nella cache delle proprietà e dei pattern di controllo per <xref:System.Windows.Automation.AutomationElement> .  
  
### <a name="activate-a-cache-request"></a>Attivare una richiesta della cache  
  
1. Creare un oggetto <xref:System.Windows.Automation.CacheRequest>.  
  
2. Specificare le proprietà e i pattern da memorizzare nella cache mediante <xref:System.Windows.Automation.CacheRequest.Add%2A>.  
  
3. Specificare l'ambito di memorizzazione nella cache impostando la proprietà <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> .  
  
4. Specificare la visualizzazione del sottoalbero impostando la proprietà <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> .  
  
5. Impostare la proprietà <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> su <xref:System.Windows.Automation.AutomationElementMode.None> se si desidera aumentare l'efficienza evitando di recuperare un riferimento completo agli oggetti. Ciò non consente di recuperare i valori correnti tali oggetti.  
  
6. Attivare la richiesta usando <xref:System.Windows.Automation.CacheRequest.Activate%2A> all'interno di un `using` blocco ( `Using` in Microsoft Visual Basic .NET).  
  
 Dopo aver ottenuto gli oggetti <xref:System.Windows.Automation.AutomationElement> o aver eseguito la sottoscrizione degli eventi, disattivare la richiesta usando <xref:System.Windows.Automation.CacheRequest.Pop%2A> (se è stata usata <xref:System.Windows.Automation.CacheRequest.Push%2A> ) oppure eliminando l'oggetto creato da <xref:System.Windows.Automation.CacheRequest.Activate%2A>. (Usare <xref:System.Windows.Automation.CacheRequest.Activate%2A> in un `using` blocco ( `Using` in Microsoft Visual Basic .NET).  
  
### <a name="cache-automationelement-properties"></a>Memorizzare nella cache le proprietà della classe AutomationElement  
  
1. Mentre è attiva una classe <xref:System.Windows.Automation.CacheRequest> , ottenere gli oggetti <xref:System.Windows.Automation.AutomationElement> mediante <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> o <xref:System.Windows.Automation.AutomationElement.FindAll%2A>oppure ottenere una classe <xref:System.Windows.Automation.AutomationElement> come origine di un evento per il quale è stata eseguita la registrazione quando la classe <xref:System.Windows.Automation.CacheRequest> è attiva. È inoltre possibile creare una cache passando <xref:System.Windows.Automation.CacheRequest> a GetUpdatedCache oppure uno dei metodi della classe <xref:System.Windows.Automation.TreeWalker> .  
  
2. Usare <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> o recuperare una proprietà dalla proprietà <xref:System.Windows.Automation.AutomationElement.Cached%2A> della classe <xref:System.Windows.Automation.AutomationElement>.  
  
### <a name="obtain-cached-patterns-and-their-properties"></a>Ottenere pattern memorizzati nella cache e le relative proprietà  
  
1. Mentre è attiva una classe <xref:System.Windows.Automation.CacheRequest> , ottenere gli oggetti <xref:System.Windows.Automation.AutomationElement> mediante <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> o <xref:System.Windows.Automation.AutomationElement.FindAll%2A>oppure ottenere una classe <xref:System.Windows.Automation.AutomationElement> come origine di un evento per il quale è stata eseguita la registrazione quando la classe <xref:System.Windows.Automation.CacheRequest> è attiva. È inoltre possibile creare una cache passando <xref:System.Windows.Automation.CacheRequest> a GetUpdatedCache oppure uno dei metodi della classe <xref:System.Windows.Automation.TreeWalker> .  
  
2. Usare <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> per recuperare un pattern memorizzato nella cache.  
  
3. Recuperare i valori di proprietà dalla proprietà `Cached` del pattern di controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente sono illustrati i vari aspetti della memorizzazione nella cache mediante l'uso di <xref:System.Windows.Automation.CacheRequest.Activate%2A> per attivare <xref:System.Windows.Automation.CacheRequest>.  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente sono illustrati i vari aspetti della memorizzazione nella cache mediante l'uso di <xref:System.Windows.Automation.CacheRequest.Push%2A> per attivare <xref:System.Windows.Automation.CacheRequest>. Tranne quando si desidera nidificare le richieste della cache, è preferibile usare <xref:System.Windows.Automation.CacheRequest.Activate%2A>.  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a>Vedere anche

- [Memorizzazione nella cache dei client di automazione interfaccia utente](caching-in-ui-automation-clients.md)
