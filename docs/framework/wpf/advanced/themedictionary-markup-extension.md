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
ms.openlocfilehash: 450956de1c7498bf2b92096b38ad2f64745a0b2d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141088"
---
# <a name="themedictionary-markup-extension"></a>Estensione di markup ThemeDictionary
Offre agli autori di controlli personalizzati o alle applicazioni che integrano controlli di terze parti un modo per caricare dizionari di risorse specifici del tema da usare per l'applicazione di stili al controllo.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
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
 Questa estensione è destinata a compilare solo un valore di proprietà specifico, ovvero <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>un valore per.  
  
 Utilizzando questa estensione, è possibile specificare un solo assembly di sole risorse contenente alcuni stili da utilizzare solo quando il tema Windows Aero viene applicato al sistema dell'utente, altri stili solo quando il tema Luna è attivo e così via. Con questa estensione, il contenuto di un dizionario risorse specifico del controllo può essere invalidato automaticamente e ricaricato in modo che venga considerato specifico per un altro tema quando necessario.  
  
 La `assemblyUri` stringa (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> valore della proprietà) costituisce la base di una convenzione di denominazione che identifica il dizionario applicabile a un particolare tema. La <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logica per `ThemeDictionary` completa la convenzione generando un URI (Uniform Resource Identifier) che punta a una particolare variante del dizionario dei temi, come contenuta in un assembly di risorse precompilato. La descrizione di questa convenzione o delle interazioni dei temi con l'applicazione generale degli stili al controllo e a livello di pagina o di applicazione come concetto, non è illustrata completamente in questa sezione. Lo scenario di base per `ThemeDictionary` l'utilizzo di consiste <xref:System.Windows.ResourceDictionary.Source%2A> nel specificare la `ResourceDictionary` proprietà di un oggetto dichiarato a livello di applicazione. Quando si specifica un URI per l'assembly tramite un' `ThemeDictionary` estensione anziché come URI diretto, la logica di estensione fornirà la logica di invalidazione che viene applicata ogni volta che il tema del sistema cambia.  
  
 La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup. Il token di stringa fornito dopo la stringa dell'identificatore `ThemeDictionary` viene assegnato come valore <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> della classe dell'estensione <xref:System.Windows.ThemeDictionaryExtension> sottostante.  
  
 `ThemeDictionary` può essere usato anche nella sintassi degli elementi oggetto. In questo caso, è necessario specificare il valore <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> della proprietà.  
  
 L'oggetto `ThemeDictionary` può anche essere utilizzato per un utilizzo dettagliato degli attributi che consente di specificare la proprietà <xref:System.Windows.Markup.StaticExtension.Member%2A> come coppia proprietà=valore:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 L'utilizzo dettagliato spesso è utile per le estensioni con più proprietà da impostare o nel caso in cui alcune proprietà siano facoltative. Poiché `ThemeDictionary` presenta una sola proprietà da impostare, obbligatoria, l'utilizzo dettagliato non è tipico.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Nell'implementazione del processore, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.ThemeDictionaryExtension> classe.  
  
 `ThemeDictionary` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usano i caratteri { e } nella sintassi degli attributi, vale a dire la convenzione in base a cui il processore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vedi anche

- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [File di dati e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md)
