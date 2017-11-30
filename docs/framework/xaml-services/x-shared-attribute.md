---
title: Attributo x:Shared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d6a9333b2267e82fc25b2a0ec4bf5dd14f644078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xshared-attribute"></a>Attributo x:Shared
Se impostato su `false`, modificare il comportamento di recupero delle risorse WPF, in modo che le richieste per la risorsa con attributa creare una nuova istanza per ogni richiesta invece di condividere la stessa istanza per tutte le richieste.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Note  
 `x:Shared`viene eseguito il mapping dello spazio dei nomi XAML del linguaggio XAML e viene riconosciuto come un elemento di linguaggio XAML valido dai servizi XAML di .NET Framework e i reader XAML. Tuttavia, le funzionalità dichiarate di `x:Shared` rilevanti solo per le applicazioni WPF e per il parser XAML di WPF. In WPF, `x:Shared` è utile come un attributo solo quando viene applicato a un oggetto che esiste all'interno di un controllo WPF <xref:System.Windows.ResourceDictionary>. Altri utilizzi generano eccezioni di analisi o altri errori, ma non hanno alcun effetto.  
  
 Il significato di `x:Shared` non è specificato nella specifica del linguaggio XAML. Altre implementazioni di XAML, ad esempio quelli basati sui servizi XAML di .NET Framework, non necessariamente supportano la condivisione delle risorse. Tali implementazioni XAML può fornire un comportamento simile nel framework di supporto usato anche `x:Shared` valori.  
  
 In WPF, il valore predefinito `x:Shared` condizione per le risorse è `true`. Questa condizione indica che qualsiasi richiesta di risorsa specificata restituisce sempre la stessa istanza.  
  
 Modifica di un oggetto che viene restituito tramite una risorsa API, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, o la modifica di un oggetto direttamente all'interno di un <xref:System.Windows.ResourceDictionary>, modifica la risorsa originale. Se i riferimenti a tale risorsa erano riferimenti a risorse dinamiche, gli utenti di tale risorsa otterranno la risorsa modificata.  
  
 Se i riferimenti alla risorsa erano riferimenti alle risorse statiche, modifiche alla risorsa dopo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tempo di elaborazione sono irrilevanti. Per ulteriori informazioni statiche e i riferimenti alle risorse dinamiche, vedere [risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Specificare in modo esplicito `x:Shared="true"` viene utilizzata raramente, perché è già il valore predefinito. Non è presente codice diretto equivalente per `x:Shared` modello a oggetti in WPF, ma può essere specificato solo in un utilizzo di XAML e deve essere elaborato da quello predefinito WPF o in un flusso del nodo XAML intermedio nel percorso di caricamento, se viene elaborato utilizzando Se XAML di .NET Framework servizi e i reader XAML.  
  
 Uno scenario per `x:Shared="false"` è se si definisce un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> derivata come una risorsa, quindi si introduce la risorsa dell'elemento in un modello di contenuto. `x:Shared="false"`Consente di introdurre più volte nella stessa raccolta di una risorsa elemento (ad esempio un <xref:System.Windows.Controls.UIElementCollection>). Senza `x:Shared="false"` non è valido perché la raccolta impone l'univocità del relativo contenuto. Tuttavia, il `x:Shared="false"` comportamento crea un'altra istanza identica della risorsa anziché restituire la stessa istanza.  
  
 Un altro scenario `x:Shared="false"` è se si utilizza un <xref:System.Windows.Freezable> risorse per i valori di animazione ma si vuole modificare la risorsa in una singola animazione.  
  
 La gestione delle stringhe di `false` non viene fatta distinzione tra maiuscole e minuscole.  
  
 In WPF, `x:Shared` valido solo nelle condizioni seguenti:  
  
-   Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi con `x:Shared` deve essere compilato. Il <xref:System.Windows.ResourceDictionary> non può essere all'interno di XAML separato o utilizzato per i temi.  
  
-   Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi non può essere annidato all'interno di altra <xref:System.Windows.ResourceDictionary>. Ad esempio, è possibile usare `x:Shared` per gli elementi in un <xref:System.Windows.ResourceDictionary> che rientra un <xref:System.Windows.Style> che è già un <xref:System.Windows.ResourceDictionary> elemento.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.ResourceDictionary>  
 [Risorse XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Elementi di base](../../../docs/framework/wpf/advanced/base-elements.md)
