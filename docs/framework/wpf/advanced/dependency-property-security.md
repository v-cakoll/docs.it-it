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
ms.openlocfilehash: eb27f3c902a0fb783d26d14d1ce494eebcffb999
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532149"
---
# <a name="dependency-property-security"></a>Sicurezza delle proprietà di dipendenza
Le proprietà di dipendenza in genere devono essere considerate come proprietà pubbliche. A causa della natura stessa del sistema di proprietà di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è impossibile avere delle garanzie di sicurezza sul valore di una proprietà di dipendenza.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Accesso e sicurezza delle proprietà wrapper e di dipendenza  
 In genere, le proprietà di dipendenza vengono implementate insieme alle proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] "wrapper" che consentono di ottenere o impostare la proprietà da un'istanza in modo più semplice. Ma i wrapper sono metodi pratici semplicemente che implementano sottostante <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> chiamate statiche utilizzate durante l'interazione con le proprietà di dipendenza. Considerando la situazione da un altro punto di vista, le proprietà sono esposte come proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] che risultano supportate da una proprietà di dipendenza piuttosto che da un campo privato. I meccanismi di sicurezza applicati ai wrapper non sono paralleli al comportamento del sistema di proprietà e all'accesso della proprietà di dipendenza sottostante. L'inserimento di una richiesta di sicurezza sul wrapper eviterà solo l'utilizzo del metodo pratico ma non impedirà le chiamate a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Analogamente, inserendo un livello di accesso protetto o privato sui wrapper non viene garantita alcuna sicurezza effettiva.  
  
 Se si sta scrivendo una proprietà di dipendenza personalizzate, è necessario dichiarare i wrapper e <xref:System.Windows.DependencyProperty> identificatore del campo come membri pubblici, in modo che i chiamanti non ottengano informazioni fuorvianti sul reale livello di accesso di tale proprietà (dal relativo archivio in corso implementato come una proprietà di dipendenza).  
  
 Per una proprietà di dipendenza personalizzate, è possibile registrare la proprietà come proprietà di dipendenza di sola lettura e si forniscono un metodo efficace per prevenire una proprietà impostata da qualsiasi utente che non dispone di un riferimento al <xref:System.Windows.DependencyPropertyKey> per tale proprietà. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
> [!NOTE]
>  La dichiarazione di una <xref:System.Windows.DependencyProperty> identificatore campo privato è consentito e può essere utilizzato presumibilmente per ridurre lo spazio dei nomi esposto immediatamente di una classe personalizzata, ma tale proprietà non deve essere considerata "privata" nello stesso senso la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] definizioni di linguaggio definiscono tale livello di accesso, per i motivi descritti nella sezione successiva.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>Esposizione di proprietà di dipendenza del sistema di proprietà  
 Non è in genere utile ed è potenzialmente fuorviante, dichiarare un <xref:System.Windows.DependencyProperty> come livello di accesso diverso da public. L'impostazione di questo livello di accesso impedisce solo che qualcuno possa ottenere un riferimento all'istanza dalla classe dichiarante. Ma esistono diversi aspetti del sistema di proprietà che verrà restituito un <xref:System.Windows.DependencyProperty> come mezzo di identificazione di una particolare proprietà esistente in un'istanza di una classe o un'istanza della classe derivata, e questo identificatore è ancora utilizzabile in un <xref:System.Windows.DependencyObject.SetValue%2A> chiamare anche Se l'identificatore statico originale è dichiarato come nonpublic. Inoltre, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> metodi virtuali ricevono le informazioni di qualsiasi proprietà di dipendenza esistente che ha modificato valore. Inoltre, il <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> metodo restituisce gli identificatori per qualsiasi proprietà nelle istanze con impostato localmente valore.  
  
### <a name="validation-and-security"></a>Convalida e sicurezza  
 Applicazione di una richiesta a un <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> e aspetta l'errore di convalida in caso di errore richiesta per impedire l'impostazione di una proprietà non è un meccanismo di sicurezza adeguato. Invalidamento del valore impostato applicato tramite <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> potrebbe essere evitato da chiamanti malintenzionati, se questi operano all'interno del dominio applicazione.  
  
## <a name="see-also"></a>Vedere anche
- [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
