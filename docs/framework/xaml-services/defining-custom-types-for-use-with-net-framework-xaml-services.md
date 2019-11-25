---
title: Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 7437add6795c1bb7f8a59807ebfc51dc2d0f987f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972016"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
Quando si definiscono tipi personalizzati che sono oggetti business o sono tipi che non hanno una dipendenza da framework specifici, è possibile seguire alcune procedure consigliate per XAML. Se si seguono queste procedure, .NET Framework servizi XAML e i relativi reader XAML e writer XAML possono individuare le caratteristiche XAML del tipo e assegnargli la rappresentazione appropriata in un flusso di nodi XAML usando il sistema di tipi XAML. In questo argomento vengono descritte le procedure consigliate per le definizioni dei tipi, le definizioni dei membri e l'attribuzione di CLR di tipi o membri.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Modelli di costruttore e definizioni di tipi per XAML  
 Per creare un'istanza di come elemento oggetto in XAML, una classe personalizzata deve soddisfare i requisiti seguenti:  
  
- La classe personalizzata deve essere pubblica ed è necessario esporre un costruttore pubblico senza parametri. Per alcune note riguardanti le strutture, vedere la sezione seguente.  
  
- La classe personalizzata non deve essere una classe annidata. Il "punto" aggiuntivo nel percorso nome completo rende ambigua la divisione dello spazio dei nomi della classe e interferisce con altre funzionalità XAML come le proprietà associate.  
  
 Se è possibile creare un'istanza di un oggetto come elemento oggetto, l'oggetto creato può compilare il form elemento proprietà di qualsiasi proprietà che accetta l'oggetto come tipo sottostante.  
  
 È comunque possibile fornire i valori oggetto per i tipi che non soddisfano questi criteri, se si Abilita un convertitore di valori. Per altre informazioni, vedere [convertitori di tipi ed estensioni di markup per XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strutture  
 Le strutture possono sempre essere costruite in XAML, per definizione CLR. Questo perché un compilatore CLR crea in modo implicito un costruttore senza parametri per una struttura. Questo costruttore inizializza tutti i valori delle proprietà in base alle impostazioni predefinite.  
  
 In alcuni casi, il comportamento di costruzione predefinito per una struttura non è auspicabile. Questo potrebbe essere dovuto al fatto che la struttura è progettata per riempire i valori e la funzione concettualmente come un'Unione. Come Unione, i valori contenuti possono avere interpretazioni che si escludono a vicenda e pertanto nessuna delle sue proprietà è impostabile. Un esempio di tale struttura nel vocabolario WPF è <xref:System.Windows.GridLength>. Tali strutture devono implementare un convertitore di tipi in modo che i valori possano essere espressi in formato di attributo, usando le convenzioni di stringa che creano le diverse interpretazioni o modalità dei valori della struttura. La struttura deve anche esporre un comportamento simile per la costruzione del codice tramite un costruttore senza parametri.  
  
### <a name="interfaces"></a>Interfacce  
 Le interfacce possono essere utilizzate come tipi sottostanti di membri. Il sistema di tipi XAML controlla l'elenco assegnabile e prevede che l'oggetto fornito come valore possa essere assegnato all'interfaccia. Non esiste alcun concetto di come l'interfaccia deve essere presentata come tipo XAML purché un tipo assegnabile pertinente supporti i requisiti di costruzione XAML.  
  
### <a name="factory-methods"></a>Metodi Factory  
 I metodi factory sono una funzionalità XAML 2009. Modificano il principio XAML che gli oggetti devono avere costruttori senza parametri. I metodi factory non sono documentati in questo argomento. Vedere [X:FactoryMethod Directive](x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerazioni  
 Le enumerazioni hanno un comportamento di conversione di tipi nativi XAML. I nomi delle costanti di enumerazione specificati in XAML vengono risolti rispetto al tipo di enumerazione sottostante e restituiscono il valore di enumerazione a un writer di oggetti XAML.  
  
 XAML supporta l'utilizzo in stile flag per le enumerazioni con <xref:System.FlagsAttribute> applicato. Per altre informazioni, vedere [sintassi XAML in dettaglio](../wpf/advanced/xaml-syntax-in-detail.md). La[sintassi XAML](../wpf/advanced/xaml-syntax-in-detail.md) viene scritta per i destinatari WPF, ma la maggior parte delle informazioni contenute in questo argomento è pertinente per XAML che non è specifico di un particolare framework di implementazione.  
  
## <a name="member-definitions"></a>Definizioni dei membri  
 I tipi possono definire membri per l'utilizzo di XAML. È possibile per i tipi che definiscono i membri che sono utilizzabili in XAML anche se il tipo specifico non è utilizzabile da XAML. Questa operazione è possibile a causa dell'ereditarietà CLR. Purché un tipo che eredita il membro supporti l'utilizzo di XAML come tipo e il membro supporti l'utilizzo di XAML per il tipo sottostante o disponga di una sintassi XAML nativa disponibile, tale membro è utilizzabile da XAML.  
  
### <a name="properties"></a>Proprietà  
 Se si definiscono le proprietà come proprietà CLR pubblica usando i `get` CLR tipici e i modelli di funzione di accesso `set` e la parola di base Language-appropriate, il sistema di tipi XAML può segnalare la proprietà come membro con le informazioni appropriate fornite per <xref:System.Xaml.XamlMember> proprietà, ad esempio <xref:System.Xaml.XamlMember.IsReadPublic%2A> e <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Le proprietà specifiche possono abilitare una sintassi del testo applicando <xref:System.ComponentModel.TypeConverterAttribute>. Per altre informazioni, vedere [convertitori di tipi ed estensioni di markup per XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 In assenza di una sintassi di testo o di una conversione XAML nativa e in assenza di ulteriori riferimenti indiretti, ad esempio l'utilizzo di un'estensione di markup, il tipo di una proprietà (<xref:System.Xaml.XamlMember.TargetType%2A> nel sistema di tipi XAML) deve essere in grado di restituire un'istanza di a un writer di oggetti XAML gestendo il tipo di destinazione come tipo CLR.  
  
 Se si usa XAML 2009, è possibile usare l' [estensione di markup x:Reference](x-reference-markup-extension.md) per fornire valori se le considerazioni precedenti non vengono soddisfatte. Tuttavia, si tratta di un problema di utilizzo maggiore rispetto a un problema di definizione del tipo.  
  
### <a name="events"></a>eventi  
 Se si definiscono gli eventi come un evento CLR pubblico, il sistema di tipi XAML può segnalare l'evento come membro con <xref:System.Xaml.XamlMember.IsEvent%2A> come `true`. Il cablaggio dei gestori di eventi non rientra nell'ambito delle funzionalità dei servizi XAML .NET Framework; Questa operazione viene lasciata a Framework e implementazioni specifici.  
  
### <a name="methods"></a>Metodi  
 Il codice inline per i metodi non è una funzionalità XAML predefinita. Nella maggior parte dei casi non si fa riferimento direttamente ai membri del metodo da XAML e il ruolo dei metodi in XAML è solo per fornire supporto per modelli XAML specifici. la [direttiva x:FactoryMethod](x-factorymethod-directive.md) è un'eccezione.  
  
### <a name="fields"></a>Campi  
 Le linee guida di progettazione CLR scoraggiano i campi non statici. Per i campi statici è possibile accedere ai valori dei campi statici solo tramite l' [estensione di markup x:static](x-static-markup-extension.md); in questo caso non si esegue alcuna operazione speciale nella definizione CLR per esporre un campo per gli utilizzi di [x:static](x-static-markup-extension.md) .  
  
## <a name="attachable-members"></a>Membri collegati  
 I membri collegati vengono esposti a XAML tramite un modello di metodo della funzione di accesso su un tipo di definizione. Non è necessario che il tipo di definizione stesso sia utilizzabile in XAML come oggetto. In realtà, un modello comune consiste nel dichiarare una classe del servizio il cui ruolo deve essere il proprietario del membro collegabile e implementare i comportamenti correlati, ma non servire nessun'altra funzione, ad esempio una rappresentazione dell'interfaccia utente. Per le sezioni seguenti, il segnaposto *PropertyName* rappresenta il nome del membro collegabile. Tale nome deve essere valido nella [Grammatica XamlName](xamlname-grammar.md).  
  
 Prestare attenzione ai conflitti di nomi tra questi modelli e altri metodi di un tipo. Se esiste un membro che corrisponde a uno dei modelli, può essere interpretato come un percorso di utilizzo del membro associabile da un processore XAML anche se non si tratta di un'intenzione.  
  
#### <a name="the-getpropertyname-accessor"></a>Funzione di accesso GetPropertyName  
 La firma per la funzione di accesso `Get`*NomeProprietà* deve essere:  
  
 `public static object Get` *PropertyName* `(object` `target` `)`  
  
- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Questa operazione può essere utilizzata per definire l'ambito dell'utilizzo del membro collegabile; gli utilizzi al di fuori dell'ambito previsto genereranno eccezioni cast non valide che vengono quindi rilevate da un errore di analisi XAML. Il nome del parametro `target` non è un requisito, ma è denominato `target` per convenzione nella maggior parte delle implementazioni.  
  
- Il valore restituito può essere specificato come tipo più specifico nell'implementazione.  
  
 Per supportare una sintassi del testo abilitata per <xref:System.ComponentModel.TypeConverter> per l'utilizzo dell'attributo del membro collegabile, applicare <xref:System.ComponentModel.TypeConverterAttribute> alla funzione di accesso `Get`*PropertyName* . L'applicazione al `get` anziché al `set` può sembrare non intuitiva. Questa convenzione può tuttavia supportare il concetto di membri di sola lettura che sono serializzabili, che risulta utile negli scenari di progettazione.  
  
#### <a name="the-setpropertyname-accessor"></a>Funzione di accesso SetPropertyName  
 La firma per la funzione di accesso set*PropertyName* deve essere:  
  
 `public static void Set` *NomeProprietà* `(object` `target` `, object` `value` `)`  
  
- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione, con la stessa logica e le stesse conseguenze descritte nella sezione precedente.  
  
- L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione.  
  
 Tenere presente che il valore di questo metodo è l'input proveniente dall'utilizzo di XAML, in genere in formato attributo. Dal form dell'attributo è necessario il supporto del convertitore di valori per una sintassi di testo e l'attributo sulla funzione di accesso `Get`*PropertyName* .  
  
### <a name="attachable-member-stores"></a>Archivi membri collegabili  
 I metodi delle funzioni di accesso non sono in genere sufficienti per fornire un mezzo per inserire i valori dei membri associabili in un oggetto grafico o per recuperare i valori dall'oggetto grafico e serializzarli in modo corretto. Per fornire questa funzionalità, è necessario che gli oggetti `target` nelle firme delle funzioni di accesso precedenti siano in grado di archiviare i valori. Il meccanismo di archiviazione deve essere coerente con il principio del membro associabile che il membro è associabile alle destinazioni in cui il membro associabile non è presente nell'elenco dei membri. .NET Framework servizi XAML fornisce una tecnica di implementazione per gli archivi membri collegabili tramite le API <xref:System.Xaml.IAttachedPropertyStore> e <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore> viene usato dai writer XAML per individuare l'implementazione dell'archivio e deve essere implementato nel tipo che rappresenta il `target` delle funzioni di accesso. Le API di <xref:System.Xaml.AttachablePropertyServices> statiche vengono utilizzate all'interno del corpo delle funzioni di accesso e fanno riferimento al membro collegabile in base al relativo <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Attributi CLR correlati a XAML  
 Attribuire correttamente i tipi, i membri e gli assembly è importante per segnalare le informazioni del sistema di tipi XAML per .NET Framework servizi XAML. Questa operazione è pertinente se si desidera che i tipi vengano utilizzati con i sistemi XAML basati direttamente sui reader XAML dei servizi XAML e .NET Framework sui writer XAML, oppure se si definisce o si utilizza un Framework che utilizza XAML basato su tali reader e writer XAML.  
  
 Per un elenco di ogni attributo correlato a XAML pertinente per il supporto XAML dei tipi personalizzati, vedere [attributi CLR correlati a XAML per tipi e librerie personalizzati](xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Utilizzo  
 Per l'utilizzo di tipi personalizzati è necessario che l'autore del markup debba eseguire il mapping di un prefisso per l'assembly e lo spazio dei nomi CLR che contiene il tipo personalizzato. Questa procedura non è documentata in questo argomento.  
  
## <a name="access-level"></a>Livello di accesso  
 XAML fornisce un mezzo per caricare e creare istanze di tipi che hanno un livello di accesso `internal`. Questa funzionalità viene fornita in modo che il codice utente possa definire i propri tipi e quindi creare un'istanza di tali classi da markup che fa anche parte dello stesso ambito del codice utente.  
  
 Un esempio di WPF è quando il codice utente definisce un <xref:System.Windows.Controls.UserControl> che deve essere utilizzato come metodo per effettuare il refactoring di un comportamento dell'interfaccia utente, ma non come parte di un meccanismo di estensione possibile che può essere implicito dichiarando la classe di supporto con `public` livello di accesso. Tale <xref:System.Windows.Controls.UserControl> può essere dichiarata con `internal` accesso se il codice di supporto viene compilato nello stesso assembly da cui viene fatto riferimento come tipo XAML.  
  
 Per un'applicazione che carica XAML con attendibilità totale e utilizza <xref:System.Xaml.XamlObjectWriter>, è sempre abilitato il caricamento delle classi con `internal` livello di accesso.  
  
 Per un'applicazione che carica XAML con attendibilità parziale, è possibile controllare le caratteristiche del livello di accesso tramite l'API <xref:System.Xaml.Permissions.XamlAccessLevel>. Inoltre, i meccanismi di rinvio, ad esempio il sistema di modelli WPF, devono essere in grado di propagare le autorizzazioni del livello di accesso e conservarle per le valutazioni del tempo di esecuzione finali; Questa operazione viene gestita internamente passando le informazioni di <xref:System.Xaml.Permissions.XamlAccessLevel>.  
  
### <a name="wpf-implementation"></a>Implementazione WPF  
 XAML WPF usa un modello di accesso parzialmente attendibile in cui se BAML viene caricato con attendibilità parziale, l'accesso è limitato a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> per l'assembly che è l'origine BAML. Per il rinvio, WPF USA <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> come meccanismo per passare le informazioni sul livello di accesso.  
  
 Nella terminologia XAML di WPF, un *tipo interno* è un tipo definito dallo stesso assembly che include anche il codice XAML di riferimento. Questo tipo può essere mappato tramite uno spazio dei nomi XAML che omette intenzionalmente la parte assembly = di un mapping, ad esempio `xmlns:local="clr-namespace:WPFApplication1"`.  Se BAML fa riferimento a un tipo interno e tale tipo ha `internal` livello di accesso, viene generata una classe `GeneratedInternalTypeHelper` per l'assembly. Se si vuole evitare `GeneratedInternalTypeHelper`, è necessario usare `public` livello di accesso oppure è necessario fattorizzare la classe pertinente in un assembly separato e rendere dipendente tale assembly.  
  
## <a name="see-also"></a>Vedere anche

- [Attributi CLR correlati a XAML per tipi e librerie personalizzati](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [Servizi XAML](index.md)
