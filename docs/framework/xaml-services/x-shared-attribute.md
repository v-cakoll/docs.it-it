---
title: Attributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: 0e9003f22c488ec35f7cc9c7be7f72c7fb8241df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622768"
---
# <a name="xshared-attribute"></a>Attributo x:Shared
Se impostato su `false`, consente di modificare il comportamento di recupero delle risorse WPF in modo che le richieste per la risorsa con attributa crea una nuova istanza per ogni richiesta invece di condividere la stessa istanza per tutte le richieste.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Note  
 `x:Shared` viene eseguito il mapping dello spazio dei nomi XAML del linguaggio XAML e viene riconosciuto come un elemento di linguaggio XAML valido per i reader XAML e dei servizi XAML di .NET Framework. Tuttavia, le funzionalità dichiarate di `x:Shared` rilevanti solo per le applicazioni WPF e per il parser XAML WPF. In WPF `x:Shared` è utile come un attributo solo quando viene applicato a un oggetto che esiste all'interno di un controllo WPF <xref:System.Windows.ResourceDictionary>. Altri utilizzi di non generano eccezioni di analisi o altri errori, ma non hanno alcun effetto.  
  
 Il significato di `x:Shared` non viene specificato nella specifica del linguaggio XAML. Altre implementazioni di XAML, ad esempio quelli basati su servizi XAML di .NET Framework, possono non offrire supporto per condivisione di risorse. Tali implementazioni XAML è stato possibile fornire un comportamento simile nel framework di supporto usato anche `x:Shared` valori.  
  
 In WPF, il valore predefinito `x:Shared` condizione per le risorse è `true`. Questa condizione indica che qualsiasi richiesta di risorsa specificato restituisce sempre la stessa istanza.  
  
 Modifica di un oggetto che viene restituito tramite una risorsa API, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>, o la modifica di un oggetto direttamente all'interno di un <xref:System.Windows.ResourceDictionary>, la risorsa originale viene modificato. Se i riferimenti a tale risorsa erano riferimenti a risorse dinamiche, i consumer di tale risorsa otterranno la risorsa modificata.  
  
 Se i riferimenti alla risorsa di riferimenti di risorse statiche, modifiche alla risorsa dopo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tempo di elaborazione sono irrilevanti. Per altre informazioni su statico e riferimenti a risorse dinamiche, vedere [risorse XAML](../wpf/advanced/xaml-resources.md).  
  
 Specificare in modo esplicito `x:Shared="true"` viene usato raramente, che è già il valore predefinito. Non è presente codice diretto equivalente per `x:Shared` in WPF modello a oggetti, ma può essere specificato solo un utilizzo di XAML e deve essere elaborato per il comportamento predefinito WPF o in un flusso del nodo XAML intermedio nel percorso di caricamento se elaborato utilizzando .NET Framework XAML Se servizi e i lettori XAML.  
  
 Per uno scenario `x:Shared="false"` campo se è possibile definire un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> derivata come risorsa e quindi si introduce la risorsa dell'elemento in un modello di contenuto. `x:Shared="false"` Consente di introdurre più volte nella stessa raccolta di una risorsa elemento (ad esempio un <xref:System.Windows.Controls.UIElementCollection>). Senza `x:Shared="false"` ciò non è valido perché la raccolta impone l'univocità del relativo contenuto. Tuttavia, il `x:Shared="false"` comportamento consente di creare un'altra istanza identica della risorsa invece di restituire la stessa istanza.  
  
 Un altro scenario `x:Shared="false"` se si usa un <xref:System.Windows.Freezable> risorsa per i valori di animazione, ma si decide di modificare la risorsa in una singola animazione.  
  
 La gestione di stringa di `false` non viene fatta distinzione tra maiuscole e minuscole.  
  
 In WPF, `x:Shared` è valido solo nelle condizioni seguenti:  
  
- Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi con `x:Shared` deve essere compilato. Il <xref:System.Windows.ResourceDictionary> non può essere all'interno di XAML loose o utilizzato per i temi.  
  
- Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi non può essere annidato all'interno di altra <xref:System.Windows.ResourceDictionary>. Ad esempio, è possibile usare `x:Shared` per gli elementi in un <xref:System.Windows.ResourceDictionary> che è all'interno di un <xref:System.Windows.Style> che è già un <xref:System.Windows.ResourceDictionary> elemento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse XAML](../wpf/advanced/xaml-resources.md)
- [Elementi di base](../wpf/advanced/base-elements.md)
