---
title: Generics in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9263edf18872f510f5f2f4e3e9cb793e45c5d0b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221600"
---
# <a name="generics-in-xaml"></a>Generics in XAML
Servizi di .NET Framework XAML come implementato in XAML fornisce il supporto per l'utilizzo di tipi generici di CLR. Questo supporto include la specifica dei vincoli di generics come argomento di tipo e applicazione dei vincoli chiamando appropriato `Add` metodo per i casi di raccolte generiche. Questo argomento descrive gli aspetti dell'utilizzo e che fanno riferimento a tipi generici in XAML.  
  
## <a name="xtypearguments"></a>X:TypeArguments  
 `x:TypeArguments` è una direttiva definita dal linguaggio XAML. Quando viene usato come un membro di un tipo XAML supportata da un tipo generico, `x:TypeArguments` passa vincoli di tipo generico per il costruttore di backup. Per la sintassi di riferimento relativo ai servizi XAML di .NET Framework per utilizzare `x:TypeArguments`, che include esempi di sintassi, vedere [direttiva X:TypeArguments](x-typearguments-directive.md).  
  
 Poiché `x:TypeArguments` accetta una stringa, e ha il supporto del convertitore di tipo, viene in genere dichiarata nell'utilizzo XAML come attributo.  
  
 Nel flusso di nodi XAML, le informazioni dichiarato da `x:TypeArguments` può essere ottenuto da <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> a un `StartObject` posizione nel flusso di nodi. Il valore restituito di <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> è un elenco di <xref:System.Xaml.XamlType> valori. Determinazione del fatto che un tipo XAML rappresenta un tipo generico può essere effettuata chiamando <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>Le regole e convenzioni della sintassi dei Generics in XAML  
 In XAML, un tipo generico deve sempre essere rappresentato come un oggetto generico vincolato; un generico non vincolato non è mai presente nel sistema di tipi XAML o un flusso del nodo XAML e non può essere rappresentato nel markup XAML. Un generico è possibile fare riferimento nella sintassi degli attributi XAML per i casi in cui è un vincolo di tipo annidato di un oggetto generico che vi fatto `x:TypeArguments`, oppure nei casi in cui `x:Type` fornisce un riferimento al tipo CLR per un tipo generico. Questa funzionalità è supportata tramite i <xref:System.Xaml.Schema.XamlTypeTypeConverter> classe definita dai servizi XAML di .NET Framework.  
  
 il XAML dell'attributo attivata dalla forma della sintassi <xref:System.Xaml.Schema.XamlTypeTypeConverter> viene modificato il tipico codice MSIL / convenzioni di sintassi CLR che utilizza le parentesi quadre per i tipi e i vincoli di generics le parentesi per il contenitore di vincolo. Per un esempio, vedere [X:TypeArguments Directive](x-typearguments-directive.md).  
  
## <a name="generics-and-xaml-2009-features"></a>Generics e le funzionalità di XAML 2009  
 Se si utilizza XAML 2009, anziché eseguire il mapping di CLR di base dei tipi per ottenere i tipi XAML per primitive di linguaggio comuni, è possibile usare [i tipi predefiniti di XAML 2009](built-in-types-for-common-xaml-language-primitives.md) come elementi informazione nella `x:TypeArguments`. Ad esempio, è possibile dichiarare la segue (prefisso di mapping non è visualizzato, ma `x` è lo spazio dei nomi XAML del linguaggio XAML di XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a>Supporto dei generics in WPF e altri framework v3.5  
 Per l'utilizzo di XAML 2006 quando la destinazione è WPF, in particolare [X:Class](x-class-directive.md) deve anche essere specificato per lo stesso elemento come `x:TypeArguments`, e tale elemento deve essere l'elemento radice in un documento XAML. L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo. Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.  
  
 Possibili soluzioni alternative per supportare gli utilizzi generici includono la definizione di un'estensione di markup personalizzata che può restituire i tipi generici o se si specifica un ritorno a capo definizione che deriva da un tipo generico, ma rende flat il vincolo generico nella propria definizione di classe della classe.  
  
 In WPF e targeting [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], è possibile usare le funzionalità di XAML 2009 con `x:TypeArguments`, ma solo per XAML loose (XAML non è compilato dal markup). Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.  
  
 Flussi di lavoro personalizzati in Windows Workflow Foundation per [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] non supportano l'utilizzo generico di XAML.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:TypeArguments](x-typearguments-directive.md)
- [Direttiva x:Class](x-class-directive.md)
- [Tipi incorporati per primitive del linguaggio XAML comuni](built-in-types-for-common-xaml-language-primitives.md)
