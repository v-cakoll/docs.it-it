---
title: Attributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071374"
---
# <a name="xshared-attribute"></a>Attributo x:Shared

Se impostato `false`su , modifica il comportamento di recupero delle risorse WPF in modo che le richieste per la risorsa con attributi creino una nuova istanza per ogni richiesta anziché condividere la stessa istanza per tutte le richieste.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Osservazioni

`x:Shared`viene mappato allo spazio dei nomi XAML del linguaggio XAML e viene riconosciuto come elemento del linguaggio XAML valido dai servizi XAML .NET e dai relativi reader XAML. Tuttavia, le `x:Shared` funzionalità indicate di sono rilevanti solo per le applicazioni WPFWPF e per il parser XAML WPF. In WPFWPF `x:Shared` è utile solo come attributo quando viene applicato <xref:System.Windows.ResourceDictionary>a un oggetto esistente all'interno di un WPFWPF . Altri utilizzi non generano eccezioni di analisi o altri errori, ma non hanno alcun effetto.

Il significato `x:Shared` di non è specificato nella specifica del linguaggio XAML. Altre implementazioni XAML, ad esempio quelle basate sui servizi XAML .NET, non forniscono necessariamente il supporto per la condivisione delle risorse. Tali implementazioni XAML potrebbero fornire un comportamento `x:Shared` simile nel framework di supporto che usava anche valori.

In WPFWPF, `x:Shared` la condizione `true`predefinita per le risorse è . Questa condizione significa che qualsiasi richiesta di risorsa specificata restituisce sempre la stessa istanza.

La modifica di un oggetto restituito tramite <xref:System.Windows.FrameworkElement.FindResource%2A>un'API di risorsa, ad esempio , o la modifica di un oggetto direttamente all'interno di un <xref:System.Windows.ResourceDictionary>oggetto , modifica la risorsa originale. Se i riferimenti a tale risorsa sono riferimenti a risorse dinamiche, i consumer di tale risorsa ottengono la risorsa modificata.

Se i riferimenti alla risorsa sono riferimenti statici alle risorse, le modifiche apportate alla risorsa dopo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] l'elaborazione sono irrilevanti. Per altre informazioni sui riferimenti alle risorse statiche e dinamiche, vedere [Risorse XAML](../fundamentals/xaml-resources-define.md).

Specificare `x:Shared="true"` in modo esplicito è raramente fatto, perché che è già l'impostazione predefinita. Non esiste un equivalente `x:Shared` diretto del codice per nel modello a oggetti WPFWPF. può essere specificato solo in un utilizzo XAML e deve essere elaborato dal comportamento WPF predefinito o in un flusso del nodo XAML intermedio nel percorso di caricamento se elaborato utilizzando i servizi XAML .NET e i relativi lettori XAML.

Uno scenario `x:Shared="false"` per è <xref:System.Windows.FrameworkElement> se <xref:System.Windows.FrameworkContentElement> si definisce una classe o derivata come risorsa e quindi si introduce la risorsa elemento in un modello di contenuto. `x:Shared="false"`consente di introdurre più volte una risorsa elemento nello <xref:System.Windows.Controls.UIElementCollection>stesso insieme , ad esempio un oggetto . In `x:Shared="false"` caso di inademi perché la raccolta impone l'univocità del contenuto. Tuttavia, `x:Shared="false"` il comportamento crea un'altra istanza identica della risorsa anziché restituire la stessa istanza.

Un altro `x:Shared="false"` scenario per <xref:System.Windows.Freezable> è se si utilizza una risorsa per i valori di animazione, ma si desidera modificare la risorsa per ogni animazione.

La gestione `false` delle stringhe di non fa distinzione tra maiuscole e minuscole.

In WPFWPF, è valido solo nelle condizioni seguenti:In WPFWPF, `x:Shared` is only valid under the following conditions:

- Che <xref:System.Windows.ResourceDictionary> contiene gli `x:Shared` elementi con deve essere compilato. L'oggetto <xref:System.Windows.ResourceDictionary> non può essere all'interno di XAML separato o utilizzato per i temi.

- Che <xref:System.Windows.ResourceDictionary> contiene gli elementi non deve <xref:System.Windows.ResourceDictionary>essere annidato all'interno di un altro file . Ad esempio, non `x:Shared` è possibile <xref:System.Windows.ResourceDictionary> utilizzare per <xref:System.Windows.Style> gli elementi <xref:System.Windows.ResourceDictionary> in un che si trova all'interno di un che è già un elemento.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse XAML](../fundamentals/xaml-resources-define.md)
- [Elementi di base](../../framework/wpf/advanced/base-elements.md)
