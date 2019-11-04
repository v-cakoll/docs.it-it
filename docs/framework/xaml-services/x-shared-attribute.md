---
title: Attributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459933"
---
# <a name="xshared-attribute"></a>Attributo x:Shared
Se impostato su `false`, modifica il comportamento di recupero delle risorse WPF in modo che le richieste per la risorsa con attributi creino una nuova istanza per ogni richiesta anziché condividere la stessa istanza per tutte le richieste.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Note  
 `x:Shared` viene eseguito il mapping allo spazio dei nomi XAML del linguaggio XAML ed è riconosciuto come elemento del linguaggio XAML valido da .NET Framework servizi XAML e dai relativi reader XAML. Tuttavia, le funzionalità dichiarate di `x:Shared` sono rilevanti solo per le applicazioni WPF e per il parser XAML WPF. In WPF, `x:Shared` è utile solo come attributo quando viene applicato a un oggetto esistente all'interno di un <xref:System.Windows.ResourceDictionary>WPF. Altri utilizzi non generano eccezioni di analisi o altri errori, ma non hanno alcun effetto.  
  
 Il significato di `x:Shared` non è specificato nella specifica del linguaggio XAML. Altre implementazioni XAML, ad esempio quelle che si basano su .NET Framework servizi XAML, non forniscono necessariamente supporto per la condivisione delle risorse. Tali implementazioni XAML possono fornire un comportamento simile nel Framework di supporto che ha utilizzato anche `x:Shared` valori.  
  
 In WPF, la condizione `x:Shared` predefinita per le risorse è `true`. Questa condizione indica che una determinata richiesta di risorse restituisce sempre la stessa istanza.  
  
 La modifica di un oggetto restituito tramite un'API di risorsa, ad esempio <xref:System.Windows.FrameworkElement.FindResource%2A>o la modifica di un oggetto direttamente all'interno di un <xref:System.Windows.ResourceDictionary>, modifica la risorsa originale. Se i riferimenti a tale risorsa sono riferimenti a risorse dinamiche, gli utenti di tale risorsa ottengono la risorsa modificata.  
  
 Se i riferimenti alla risorsa sono riferimenti a risorse statiche, le modifiche apportate alla risorsa dopo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tempo di elaborazione sono irrilevanti. Per ulteriori informazioni sui riferimenti a risorse statiche e dinamiche, vedere [risorse XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 L'impostazione esplicita di `x:Shared="true"` viene eseguita raramente, perché è già quella predefinita. Non esiste alcun equivalente di codice diretto per `x:Shared` nel modello a oggetti WPF; può essere specificato solo in un utilizzo XAML e deve essere elaborato dal comportamento WPF predefinito o in un flusso del nodo XAML intermedio sul percorso di caricamento, se elaborato utilizzando .NET Framework servizi XAML e i relativi reader XAML.  
  
 Uno scenario per `x:Shared="false"` è se si definisce una <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> classe derivata come risorsa e quindi si introduce la risorsa dell'elemento in un modello di contenuto. `x:Shared="false"` consente l'introduzione di una risorsa elemento più volte nella stessa raccolta, ad esempio <xref:System.Windows.Controls.UIElementCollection>. Senza `x:Shared="false"` questa operazione non è valida perché la raccolta applica l'univocità del contenuto. Tuttavia, il comportamento del `x:Shared="false"` crea un'altra istanza identica della risorsa anziché restituire la stessa istanza.  
  
 Un altro scenario per `x:Shared="false"` è se si usa una risorsa <xref:System.Windows.Freezable> per i valori di animazione, ma si vuole modificare la risorsa per ogni singola animazione.  
  
 La gestione delle stringhe di `false` non fa distinzione tra maiuscole e minuscole.  
  
 In WPF `x:Shared` è valido solo nelle condizioni seguenti:  
  
- È necessario compilare il <xref:System.Windows.ResourceDictionary> contenente gli elementi con `x:Shared`. Il <xref:System.Windows.ResourceDictionary> non può trovarsi all'interno di XAML separato o usato per i temi.  
  
- Il <xref:System.Windows.ResourceDictionary> che contiene gli elementi non deve essere annidato all'interno di un'altra <xref:System.Windows.ResourceDictionary>. Ad esempio, non è possibile usare `x:Shared` per gli elementi di un <xref:System.Windows.ResourceDictionary> che si trova all'interno di un <xref:System.Windows.Style> che è già un elemento <xref:System.Windows.ResourceDictionary>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Elementi di base](../wpf/advanced/base-elements.md)
