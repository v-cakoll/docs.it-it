---
title: Attributi nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: b32e4f87e953438a3bb11569445a9270e11c7922
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732135"
---
# <a name="attributes-in-windows-forms-controls"></a>Attributi nei controlli Windows Form
.NET Framework offre un'ampia gamma di attributi che è possibile applicare ai membri dei controlli e dei componenti personalizzati. Alcuni di questi attributi influiscono sul comportamento in fase di esecuzione di una classe, mentre altri influiscono sul comportamento in fase di progettazione.  
  
## <a name="attributes-for-control-and-component-properties"></a>Attributi per le proprietà del controllo e del componente  
 La tabella seguente illustra gli attributi che è possibile applicare alle proprietà o ad altri membri dei componenti e dei controlli personalizzati. Per un esempio che usa molti di questi attributi vedere [Procedura: applicare attributi nei controlli Windows Form](how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Specifica il valore per passare a una proprietà che determini il proprio valore da un'altra origine. Questo concetto è noto come *ambiente*.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Indica se visualizzare una proprietà o un evento in una finestra **Proprietà**.|  
|<xref:System.ComponentModel.CategoryAttribute>|Specifica il nome della categoria in cui raggruppare la proprietà o l'evento quando viene visualizzato in un controllo <xref:System.Windows.Forms.PropertyGrid> impostato sulla modalità di <xref:System.Windows.Forms.PropertySort.Categorized>.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Specifica il valore predefinito per una proprietà.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Specifica una descrizione per una proprietà o un evento.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Specifica il nome visualizzato per una proprietà, un evento o un metodo `public void` che non accetta argomenti.|  
|<xref:System.ComponentModel.EditorAttribute>|Specifica l'editor da usare per modificare una proprietà.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Specifica che una proprietà o un metodo è visualizzabile in un editor.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Specifica la parola chiave del contesto per una classe o un membro.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Specifica se è necessario localizzare una proprietà.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Indica che la rappresentazione di testo di un oggetto è nascosta da caratteri quali gli asterischi.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Specifica se la proprietà a cui è associato questo attributo è di sola lettura o di lettura/scrittura in fase di progettazione.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Indica che la griglia delle proprietà deve essere aggiornata quando cambia il valore della proprietà associata.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Specifica il tipo da utilizzare come convertitore per l'oggetto a cui l'attributo è associato.|  
  
## <a name="attributes-for-data-binding-properties"></a>Attributi per le proprietà dell'associazione di dati  
 La tabella seguente illustra gli attributi che è possibile applicare per specificare le modalità in cui i componenti e i controlli personalizzati interagiscono con l'associazione dei dati.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Specifica se una proprietà viene in genere usata per l'associazione.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Specifica l'origine dati e le proprietà dei membri dati per un componente.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Specifica la proprietà di associazione predefinita per un componente.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Specifica l'origine dati e le proprietà dei membri dati per un componente.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Consente il reindirizzamento degli attributi.|  
  
## <a name="attributes-for-classes"></a>Attributi per classi  
 La tabella seguente illustra gli attributi che è possibile applicare per specificare il comportamento dei componenti e dei controlli personalizzati in fase di progettazione.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Specifica l'evento predefinito per un componente.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Specifica la proprietà predefinita per un componente.|  
|<xref:System.ComponentModel.DesignerAttribute>|Specifica la classe usata per implementare i servizi in fase di progettazione per un componente.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Specifica che la finestra di progettazione di una classe appartiene a una determinata categoria.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Rappresenta un attributo di un elemento della casella degli strumenti.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Specifica la stringa del filtro e il tipo di filtro da usare per un elemento della casella degli strumenti.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- [Procedura: Applicare attributi nei controlli Windows Form](how-to-apply-attributes-in-windows-forms-controls.md)
- [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
