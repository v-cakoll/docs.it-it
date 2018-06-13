---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: faef74c57ac5ff9e3d4162accfc6552db55715bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563584"
---
# <a name="generics-in-xaml"></a>Generics in XAML
Servizi .NET Framework XAML, come implementato in System. XAML fornisce supporto per l'utilizzo di tipi generici di CLR. Questo supporto include la specifica dei vincoli dei generics come argomento di tipo e l'applicazione dei vincoli mediante la chiamata appropriata `Add` metodo per casi di raccolte generiche. Questo argomento descrive gli aspetti e fanno riferimento a tipi generici in XAML.  
  
## <a name="xtypearguments"></a>X:TypeArguments  
 `x:TypeArguments` una direttiva è definita dal linguaggio XAML. Quando viene utilizzata come membro di un tipo XAML supportato da un tipo generico, `x:TypeArguments` passa vincoli di tipo generico al costruttore di supporto. Per informazioni sulla sintassi di riferimento relativo ai servizi XAML di .NET Framework utilizzare `x:TypeArguments`, che include esempi di sintassi, vedere [direttiva X:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
 Poiché `x:TypeArguments` accetta una stringa e il supporto del convertitore di tipo, è in genere viene dichiarato nell'utilizzo XAML come attributo.  
  
 Nel flusso del nodo XAML, le informazioni dichiarate tramite `x:TypeArguments` possono essere ottenuti dalla <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> in un `StartObject` posizione nel flusso del nodo. Il valore restituito di <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> è un elenco di <xref:System.Xaml.XamlType> valori. Per stabilire se un tipo XAML rappresenti un tipo generico può essere eseguita chiamando <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Regole e convenzioni della sintassi per i Generics in XAML  
 In XAML, un tipo generico deve sempre essere rappresentato come generico vincolato; un generico non vincolato non è mai presente nel sistema di tipi XAML o un flusso del nodo XAML e non può essere rappresentato nel markup XAML. È possibile fare riferimento un oggetto generico nella sintassi degli attributi XAML nei casi in cui è un vincolo di tipo annidato di un oggetto generico a cui fa riferimento `x:TypeArguments`, o nei casi in cui `x:Type` fornisce un riferimento al tipo CLR per un tipo generico. Questa funzionalità è supportata tramite la <xref:System.Xaml.Schema.XamlTypeTypeConverter> classe definita dai servizi XAML di .NET Framework.  
  
 Il codice XAML attributo attivata dalla forma della sintassi <xref:System.Xaml.Schema.XamlTypeTypeConverter> modifica tipico MSIL / convenzione sintassi CLR che utilizza le parentesi quadre per i tipi e i vincoli dei generics le parentesi per il contenitore di vincolo. Per un esempio, vedere [direttiva X:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Generics e le funzionalità di XAML 2009  
 Se si utilizza XAML 2009, anziché eseguire il mapping CLR tipi di base di ottenere tipi XAML per le primitive di linguaggio comune, è possibile utilizzare [tipi incorporati di XAML 2009](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) come elementi informazione nella `x:TypeArguments`. Ad esempio, è possibile dichiarare le operazioni seguenti (prefisso di mapping non è visualizzato, ma `x` lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Supporto dei generics in WPF e altri Framework v 3.5  
 Per l'utilizzo di XAML 2006 quando la destinazione in modo specifico di WPF, [X:Class](../../../docs/framework/xaml-services/x-class-directive.md) deve inoltre essere disponibile nello stesso elemento come `x:TypeArguments`, e tale elemento deve essere l'elemento radice in un documento XAML. L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Possibili soluzioni alternative per supportare gli utilizzi generici includono la definizione di un'estensione di markup personalizzata che può restituire tipi generici o fornendo un ritorno a capo definizione che deriva da un tipo generico ma appiattisce il vincolo generico nella propria definizione di classe della classe.  
  
 In WPF e di destinazione [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], è possibile utilizzare le funzionalità di XAML 2009 con `x:TypeArguments`, ma solo per XAML separato (XAML non compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 Flussi di lavoro personalizzati in Windows Workflow Foundation per [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] non supportano l'utilizzo XAML generico.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [Direttiva x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Tipi incorporati per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
