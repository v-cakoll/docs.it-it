---
title: Sicurezza delle proprietà di dipendenza
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: 825b2a3dc79300f0cc26514398b8de0abee64fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540504"
---
# <a name="dependency-property-security"></a>Sicurezza delle proprietà di dipendenza
Le proprietà di dipendenza in genere devono essere considerate come proprietà pubbliche. A causa della natura stessa del sistema di proprietà di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è impossibile avere delle garanzie di sicurezza sul valore di una proprietà di dipendenza.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Accesso e sicurezza delle proprietà wrapper e di dipendenza  
 In genere, le proprietà di dipendenza vengono implementate insieme alle proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] "wrapper" che consentono di ottenere o impostare la proprietà da un'istanza in modo più semplice. I wrapper sono metodi utili semplicemente che implementano sottostante <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> chiamate statiche che vengono utilizzate durante l'interazione con le proprietà di dipendenza. Considerando la situazione da un altro punto di vista, le proprietà sono esposte come proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] che risultano supportate da una proprietà di dipendenza piuttosto che da un campo privato. I meccanismi di sicurezza applicati ai wrapper non sono paralleli al comportamento del sistema di proprietà e all'accesso della proprietà di dipendenza sottostante. Inserimento di una richiesta di sicurezza sul wrapper consente di evitare l'utilizzo del metodo pratico ma non impedisce chiamate a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Analogamente, inserendo un livello di accesso protetto o privato sui wrapper non viene garantita alcuna sicurezza effettiva.  
  
 Se si siano scrivendo le proprietà di dipendenza, è necessario dichiarare i wrapper e <xref:System.Windows.DependencyProperty> campo dell'identificatore come membri pubblici, in modo che i chiamanti non ottengano informazioni fuorvianti sul livello di accesso true di tale proprietà (dal relativo archivio da implementato come una proprietà di dipendenza).  
  
 Per una proprietà di dipendenza personalizzata, è possibile registrare la proprietà come proprietà di dipendenza di sola lettura e questo forniscono un mezzo efficace di una proprietà viene impostata da qualsiasi utente che non contiene un riferimento a impedire il <xref:System.Windows.DependencyPropertyKey> per tale proprietà. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  Dichiarazione di un <xref:System.Windows.DependencyProperty> identificatore campo privato non è consentito ed e può anche essere utilizzato per ridurre lo spazio dei nomi esposto immediatamente di una classe personalizzata, ma tale proprietà non deve essere considerata "privata" nel senso stesso come il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] definizioni di linguaggio definiscono tale livello di accesso, per i motivi descritti nella sezione successiva.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Esposizione di proprietà di dipendenza del sistema di proprietà  
 Non è in genere utile ed è potenzialmente fuorviante per dichiarare un <xref:System.Windows.DependencyProperty> come livello di accesso diverso da public. L'impostazione di questo livello di accesso impedisce solo che qualcuno possa ottenere un riferimento all'istanza dalla classe dichiarante. Ma esistono diversi aspetti del sistema di proprietà che verrà restituito un <xref:System.Windows.DependencyProperty> come i mezzi di identificazione di una determinata proprietà mentre è presente in un'istanza di una classe o un'istanza della classe derivata, questo identificatore è ancora utilizzabile in un <xref:System.Windows.DependencyObject.SetValue%2A> anche chiamare Se l'identificatore originale statico viene dichiarato come nonpublic. Inoltre, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> metodi virtuali ricevono le informazioni di qualsiasi proprietà di dipendenza esistente che ha modificato valore. Inoltre, il <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> metodo restituisce gli identificatori per qualsiasi proprietà nelle istanze con impostato localmente valore.  
  
### <a name="validation-and-security"></a>Convalida e sicurezza  
 Applicazione di una richiesta per un <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> e prevede l'errore di convalida in caso di errore per impedire l'impostazione di una proprietà richiesta non è un meccanismo di sicurezza adeguato. Invalidamento del valore impostato per applicare <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> potrebbe essere evitato da chiamanti malintenzionati, se questi operano all'interno del dominio applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
