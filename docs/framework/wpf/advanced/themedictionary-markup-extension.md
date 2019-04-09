---
title: Estensione di markup ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: ad2248c791fadc5363d90ff496d5e040f6036ab3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132093"
---
# <a name="themedictionary-markup-extension"></a>Estensione di markup ThemeDictionary
Offre agli autori di controlli personalizzati o alle applicazioni che integrano controlli di terze parti un modo per caricare dizionari di risorse specifici del tema da usare per l'applicazione di stili al controllo.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`assemblyUri`|[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] dell'assembly contenente le informazioni sul tema. In genere, si tratta di un URI di tipo pack che fa riferimento a un assembly del pacchetto più grande. Le risorse di assembly e gli URI di tipo pack semplificano i problemi di distribuzione. Per altre informazioni, vedere [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Note  
 Questa estensione deve compilare un solo valore di proprietà specifici: un valore per <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.  
  
 Usando questa estensione è possibile specificare un singolo assembly di sole risorse contenente alcuni stili da usare solo quando il tema [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)] viene applicato al sistema dell'utente. Gli altri stili possono essere usati quando è attivo il tema Luna e così via. Con questa estensione, il contenuto di un dizionario risorse specifico del controllo può essere invalidato automaticamente e ricaricato in modo che venga considerato specifico per un altro tema quando necessario.  
  
 Il `assemblyUri` stringa (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> valore della proprietà) costituisce la base di una convenzione di denominazione che identifica il dizionario applicato a un particolare tema. Il <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> per la logica `ThemeDictionary` completa la convenzione generando un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] che punta a una variante di dizionario particolare dei temi, contenuta all'interno di un assembly di risorse precompilato. La descrizione di questa convenzione o delle interazioni dei temi con l'applicazione generale degli stili al controllo e a livello di pagina o di applicazione come concetto, non è illustrata completamente in questa sezione. Lo scenario di base per l'utilizzo `ThemeDictionary` consiste nello specificare il <xref:System.Windows.ResourceDictionary.Source%2A> proprietà di un `ResourceDictionary` dichiarato a livello di applicazione. Quando si fornisce un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per l'assembly tramite un'estensione `ThemeDictionary` anziché un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] diretto, la logica dell'estensione fornirà la logica di invalidazione applicata in occasione di tutte le modifiche del tema del sistema.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `ThemeDictionary` viene assegnato come valore <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> della classe dell'estensione <xref:System.Windows.ThemeDictionaryExtension> sottostante.  
  
 `ThemeDictionary` può essere utilizzato anche nella sintassi degli elementi oggetto. In questo caso, specificando il valore di <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> proprietà è obbligatoria.  
  
 `ThemeDictionary` è anche utilizzabile in un utilizzo dettagliato degli attributi che specifica il <xref:System.Windows.Markup.StaticExtension.Member%2A> proprietà come proprietà di = coppia valore:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `ThemeDictionary` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] l'implementazione del processore, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.ThemeDictionaryExtension> classe.  
  
 `ThemeDictionary` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica di XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [File di dati e di risorse dell'applicazione WPF.](../app-development/wpf-application-resource-content-and-data-files.md)
