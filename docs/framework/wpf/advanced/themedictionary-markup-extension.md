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
ms.openlocfilehash: f6ba0fe45aa11063c79d673b26794072968f4200
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646180"
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
|`assemblyUri`|URI (Uniform Resource Identifier) dell'assembly che contiene informazioni sul tema. In genere, si tratta di un URI di tipo pack che fa riferimento a un assembly del pacchetto più grande. Le risorse di assembly e gli URI di tipo pack semplificano i problemi di distribuzione. Per altre informazioni, vedere [URI di tipo pack in WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Osservazioni  
 Questa estensione ha lo scopo di riempire un <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>solo valore di proprietà specifico: un valore per .  
  
 Utilizzando questa estensione, è possibile specificare un singolo assembly di sole risorse che contiene alcuni stili da utilizzare solo quando il tema Di Aero viene applicato al sistema dell'utente, altri stili solo quando il tema Luna è attivo e così via. Con questa estensione, il contenuto di un dizionario risorse specifico del controllo può essere invalidato automaticamente e ricaricato in modo che venga considerato specifico per un altro tema quando necessario.  
  
 La `assemblyUri` stringa<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> ( valore della proprietà) costituisce la base di una convenzione di denominazione che identifica il dizionario applicato per un tema specifico. La <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logica `ThemeDictionary` per completare la convenzione generando un URI (Uniform Resource Identifier) che punta a una particolare variante del dizionario dei temi, contenuta in un assembly di risorse precompilato. La descrizione di questa convenzione o delle interazioni dei temi con l'applicazione generale degli stili al controllo e a livello di pagina o di applicazione come concetto, non è illustrata completamente in questa sezione. Lo scenario di `ThemeDictionary` base per <xref:System.Windows.ResourceDictionary.Source%2A> l'utilizzo consiste nello specificare la proprietà di un `ResourceDictionary` oggetto dichiarato a livello di applicazione. Quando si fornisce un URI `ThemeDictionary` per l'assembly tramite un'estensione anziché come URI diretto, la logica di estensione fornirà la logica di invalidazione che viene applicata ogni volta che il tema di sistema viene modificato.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `ThemeDictionary` viene assegnato come valore <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> della classe dell'estensione <xref:System.Windows.ThemeDictionaryExtension> sottostante.  
  
 `ThemeDictionary` può essere usato anche nella sintassi degli elementi oggetto. In questo caso, è necessario <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> specificare il valore della proprietà.  
  
 L'oggetto `ThemeDictionary` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.Markup.StaticExtension.Member%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `ThemeDictionary` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 Nell'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore, la gestione per <xref:System.Windows.ThemeDictionaryExtension> questa estensione di markup è definita dalla classe .  
  
 `ThemeDictionary` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [File di dati e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md)
