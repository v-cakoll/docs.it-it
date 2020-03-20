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
ms.openlocfilehash: f5640b348ccd68819052f58756489489371862d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186387"
---
# <a name="dependency-property-security"></a>Sicurezza delle proprietà di dipendenza
Le proprietà di dipendenza in genere devono essere considerate come proprietà pubbliche. A causa della natura stessa del sistema di proprietà di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], è impossibile avere delle garanzie di sicurezza sul valore di una proprietà di dipendenza.  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Accesso e sicurezza delle proprietà wrapper e di dipendenza  
 In genere, le proprietà di dipendenza vengono implementate insieme alle proprietà di Common Language Runtime (CLR) "wrapper" che semplificano il recupero o l'impostazione della proprietà da un'istanza. Ma i wrapper sono in realtà solo <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> metodi pratici che implementano le chiamate sottostanti e statiche che vengono utilizzate quando si interagisce con le proprietà di dipendenza. Pensando in un altro modo, le proprietà vengono esposte come proprietà CLR (Common Language Runtime) supportate da una proprietà di dipendenza anziché da un campo privato. I meccanismi di sicurezza applicati ai wrapper non sono paralleli al comportamento del sistema di proprietà e all'accesso della proprietà di dipendenza sottostante. L'inserimento di una richiesta di sicurezza nel wrapper impedirà <xref:System.Windows.DependencyObject.GetValue%2A> solo <xref:System.Windows.DependencyObject.SetValue%2A>l'utilizzo del metodo di convenienza, ma non impedirà le chiamate a o . Analogamente, inserendo un livello di accesso protetto o privato sui wrapper non viene garantita alcuna sicurezza effettiva.  
  
 Se si scrivono proprietà di dipendenza personalizzate, è <xref:System.Windows.DependencyProperty> necessario dichiarare i wrapper e il campo dell'identificatore come membri pubblici, in modo che i chiamanti non otziano informazioni fuorvianti sul livello di accesso reale di tale proprietà (a causa dell'implementazione dell'archivio come proprietà di dipendenza).  
  
 Per una proprietà di dipendenza personalizzata, è possibile registrare la proprietà come proprietà di dipendenza di sola lettura e ciò fornisce <xref:System.Windows.DependencyPropertyKey> un mezzo efficace per impedire che una proprietà venga impostata da chiunque non contenga un riferimento a tale proprietà. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](read-only-dependency-properties.md).  
  
> [!NOTE]
> Dichiarare un <xref:System.Windows.DependencyProperty> campo identificatore privato non è vietato e può essere utilizzato per ridurre lo spazio dei nomi immediatamente esposto di una classe personalizzata, ma tale proprietà non deve essere considerata "privata" nello stesso senso delle definizioni di linguaggio CLR (Common Language Runtime) che definiscono tale livello di accesso, per i motivi descritti nella sezione successiva.  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>Esposizione di proprietà di dipendenza del sistema di proprietà  
 Non è generalmente utile, ed è potenzialmente <xref:System.Windows.DependencyProperty> fuorviante, dichiarare un livello di accesso diverso da quello pubblico. L'impostazione di questo livello di accesso impedisce solo che qualcuno possa ottenere un riferimento all'istanza dalla classe dichiarante. Esistono tuttavia diversi aspetti del sistema di <xref:System.Windows.DependencyProperty> proprietà che restituiranno un come mezzo per identificare una particolare proprietà come esiste in un'istanza di una classe o di un'istanza di una classe derivata e questo identificatore è ancora utilizzabile in una <xref:System.Windows.DependencyObject.SetValue%2A> chiamata anche se l'identificatore statico originale viene dichiarato come non pubblico. Inoltre, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> i metodi virtuali ricevono informazioni su qualsiasi proprietà di dipendenza esistente che ha modificato il valore. Inoltre, il <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> metodo restituisce gli identificatori per qualsiasi proprietà nelle istanze con un valore impostato localmente.  
  
### <a name="validation-and-security"></a>Convalida e sicurezza  
 L'applicazione di <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> una richiesta a un oggetto e la attesa dell'errore di convalida in caso di errore della richiesta per impedire l'impostazione di una proprietà non è un meccanismo di sicurezza adeguato. L'invalidazione del valore <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> impostato applicata tramite potrebbe anche essere eliminata da chiamanti malintenzionati, se tali chiamanti operano all'interno del dominio applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
