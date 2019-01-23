---
title: Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: 672660f73e9e6faf25985a651290e979f9deb9f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492507"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework
Quando si definiscono tipi personalizzati che sono oggetti business o i tipi che non è una dipendenza su Framework specifici, esistono alcune procedure consigliate per XAML è possibile seguire. Se si seguono queste procedure, dei servizi XAML di .NET Framework e relativi reader XAML e writer XAML può individuare le caratteristiche XAML del tipo in uso e assegnargli rappresentazione appropriata in un flusso di nodi XAML usando il sistema di tipi XAML. In questo argomento descrive le procedure consigliate per le definizioni dei tipi, le definizioni dei membri e assegnazione di attributi CLR di tipi o membri.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>Modelli di costruttore e definizioni di tipi per XAML  
 Per creare un'istanza come elemento oggetto in XAML, una classe personalizzata deve soddisfare i requisiti seguenti:  
  
-   La classe personalizzata deve essere pubblica e deve esporre un costruttore pubblico (senza parametri) predefinito. Per alcune note riguardanti le strutture, vedere la sezione seguente.  
  
-   La classe personalizzata non deve essere una classe annidata. Aggiuntivo "dot" nel percorso del nome completo rende ambiguo la divisione di spazio dei nomi di classe e interferisce con altre funzionalità XAML, ad esempio le proprietà associate.  
  
 Se è possibile creare istanze di un oggetto come elemento oggetto, l'oggetto creato è riempire il form elemento di proprietà di qualsiasi proprietà che accettano l'oggetto come relativo tipo sottostante.  
  
 È comunque possibile fornire valori dell'oggetto per i tipi che non soddisfano questi criteri, se si abilita un convertitore di valori. Per altre informazioni, vedere [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
### <a name="structures"></a>Strutture  
 Le strutture sono sempre in grado di costruire in XAML, per definizione di CLR. Questo avviene perché un compilatore CLR crea implicitamente un costruttore predefinito per una struttura. Questo costruttore inizializza tutti i valori di proprietà sui valori predefiniti.  
  
 In alcuni casi, il comportamento di costruzione predefinita per una struttura non è consigliabile. È possibile perché la struttura è destinata a inserire valori e funzioni a livello concettuale come un'unione. Come un'unione, i valori contenuti potrebbero avere interpretazioni si escludono a vicenda e di conseguenza, nessuna delle relative proprietà possono essere impostata. Un esempio di tale struttura nel vocabolario WPF è <xref:System.Windows.GridLength>. Tali strutture devono implementare un convertitore di tipi in modo che i valori possono essere espressi sotto forma di attributo tramite convenzioni di stringa che creano le interpretazioni o modalità diverse dei valori di struttura. La struttura deve anche esporre un comportamento simile per la costruzione del codice tramite un costruttore non predefinito.  
  
### <a name="interfaces"></a>Interfacce  
 Le interfacce possono essere utilizzate come tipi sottostanti dei membri. Il sistema di tipi XAML controlla l'elenco può essere assegnato e si aspetta che l'oggetto fornito come valore può essere assegnato all'interfaccia. Non vi è alcun concetto di modalità di presentazione dell'interfaccia come tipo XAML fino a quando un tipo assegnabile rilevante supportino i requisiti di costruzione di XAML.  
  
### <a name="factory-methods"></a>Metodi factory  
 I metodi factory sono una funzionalità di XAML 2009. Modificare il principio XAML che gli oggetti devono avere costruttori predefiniti. I metodi factory non sono documentati in questo argomento. Visualizzare [direttiva X:FactoryMethod](../../../docs/framework/xaml-services/x-factorymethod-directive.md).  
  
## <a name="enumerations"></a>Enumerazioni  
 Le enumerazioni dispongono di comportamento di conversione di tipo nativo di XAML. I nomi delle costanti di enumerazione specificati nel XAML vengono risolti in base al tipo di enumerazione sottostante e restituisce il valore di enumerazione a un writer di oggetti XAML.  
  
 XAML supporta l'utilizzo di flag di stile per le enumerazioni con <xref:System.FlagsAttribute> applicato. Per altre informazioni, vedere [XAML descrizione dettagliata della sintassi](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md). ([XAML descrizione dettagliata della sintassi](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) è stata scritta per il gruppo di destinatari WPF, ma la maggior parte delle informazioni in questo argomento sono rilevanti per XAML che non è specifico per un particolare framework di implementazione.)  
  
## <a name="member-definitions"></a>Definizioni dei membri  
 Tipi possono definire i membri per l'utilizzo XAML. È possibile che i tipi che definiscono i membri che possono essere utilizzati con XAML anche se quel tipo specifico non è utilizzabile con XAML. Ciò è possibile a causa dell'ereditarietà di CLR. Purché alcuni tipo che eredita il membro supporta l'utilizzo XAML come tipo e il membro supporta l'utilizzo di XAML per il relativo tipo sottostante o presenta una sintassi XAML nativa disponibile, tale membro è utilizzabile con XAML.  
  
### <a name="properties"></a>Proprietà  
 Se si definiscono proprietà come proprietà CLR pubblica usando CLR tipico `get` e `set` modelli di funzione di accesso e parole chiave appropriata per la lingua, il sistema di tipi XAML può segnalare la proprietà come un membro con le informazioni appropriate previste <xref:System.Xaml.XamlMember> proprietà, ad esempio <xref:System.Xaml.XamlMember.IsReadPublic%2A> e <xref:System.Xaml.XamlMember.IsWritePublic%2A>.  
  
 Le proprietà specifiche è possono abilitare una sintassi del testo applicando <xref:System.ComponentModel.TypeConverterAttribute>. Per altre informazioni, vedere [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In assenza di una sintassi del testo o di conversione nativa XAML e in assenza di un'ulteriore riferimento indiretto, ad esempio un utilizzo dell'estensione di markup, il tipo di una proprietà (<xref:System.Xaml.XamlMember.TargetType%2A> in XAML il sistema di tipi) deve essere in grado di restituire un'istanza a un writer di oggetti XAML, considerando la t tipo arget come tipo CLR.  
  
 Se si usa XAML 2009 [X:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md) possono essere usati per fornire i valori se non vengono soddisfatte le considerazioni precedenti, tuttavia, che è più di un problema di utilizzo rispetto a un problema di definizione del tipo.  
  
### <a name="events"></a>Eventi  
 Se si definiscono gli eventi come un evento pubblico CLR, il sistema di tipi XAML può segnalare l'evento come un membro con <xref:System.Xaml.XamlMember.IsEvent%2A> come `true`. Collegare i gestori di eventi non è nell'ambito di funzionalità di servizi XAML di .NET Framework; Questo è lasciato a Framework specifici e implementazioni.  
  
### <a name="methods"></a>Metodi  
 Il codice inline per metodi non è una funzionalità XAML predefinito. Nella maggior parte dei casi non si direttamente fa riferimento a membri del metodo da XAML e il ruolo di metodi in XAML è solo per fornire supporto per specifici modelli XAML. [Direttiva X:FactoryMethod](../../../docs/framework/xaml-services/x-factorymethod-directive.md) è un'eccezione.  
  
### <a name="fields"></a>Campi  
 Linee guida di progettazione CLR scoraggiare i campi non statici. Per i campi statici, è possibile accedere i valori dei campi statici solo attraverso [estensione di Markup X:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md); in questo caso non si sta eseguendo alcuna operazione speciale nella definizione del CLR di un campo per esporre [X:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md) utilizzi.  
  
## <a name="attachable-members"></a>Membri associabili  
 I membri associabili sono esposte a XAML tramite un modello di metodo della funzione di accesso su un tipo di definizione. Tipo di definizione stesso non è necessario per poter essere usato per XAML come oggetto. In effetti, un modello comune consiste nel dichiarare una classe di servizio con ruolo proprietario membro associabile e implementare i comportamenti correlati, ma anche non servire alcuna altra funzione, ad esempio una rappresentazione dell'interfaccia utente. Per le sezioni seguenti, il segnaposto *PropertyName* rappresenta il nome del membro associabile. Tale nome deve essere valido nella [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 Prestare attenzione dei conflitti di nomi tra questi modelli e altri metodi di un tipo. Se esiste un membro che corrisponde a uno dei modelli, si può essere interpretato come un percorso di utilizzo del membro associabile da un processore XAML anche se non si intende.  
  
#### <a name="the-getpropertyname-accessor"></a>Funzione di accesso GetPropertyName  
 La firma per la funzione di accesso `Get`*NomeProprietà* deve essere:  
  
 `public static object Get` *PropertyName* `(object` `target` `)`  
  
-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. È possibile utilizzare questo per definire l'ambito di utilizzo del membro associabile; gli utilizzi rientrano nell'ambito desiderato genererà le eccezioni di cast non valido che vengono quindi replicate da un errore di analisi XAML. Il nome del parametro `target` non è un requisito, ma è denominato `target` per convenzione nella maggior parte delle implementazioni.  
  
-   Il valore restituito può essere specificato come tipo più specifico nell'implementazione.  
  
 Per supportare un <xref:System.ComponentModel.TypeConverter> sintassi del testo abilitata per l'utilizzo dell'attributo del membro associabile, applicare <xref:System.ComponentModel.TypeConverterAttribute> per il `Get` *PropertyName* della funzione di accesso. Applicazione al `get` anziché il `set` può sembrare non intuitiva; tuttavia, questa convenzione può supportare il concetto di sola lettura i membri associabili serializzabili, che risulta utile negli scenari di progettazione.  
  
#### <a name="the-setpropertyname-accessor"></a>La funzione di accesso SetPropertyName  
 La firma per il Set*PropertyName* della funzione di accesso deve essere:  
  
 `public static void Set` *NomeProprietà* `(object` `target` `, object` `value` `)`  
  
-   Il `target` oggetto può essere specificato come un tipo più specifico nell'implementazione, con lo stesso per la logica e conseguenze come descritto nella sezione precedente.  
  
-   L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione.  
  
 Tenere presente che il valore per questo metodo è l'input proveniente dall'uso di XAML, in genere sotto forma di attributo. Dalla forma di attributo deve essere presente il supporto di convertitore di tipi di valore per una sintassi del testo e attributo il `Get` *NomeProprietà* della funzione di accesso.  
  
### <a name="attachable-member-stores"></a>Archivi dei membri associabili  
 I metodi della funzione di accesso in genere non sono sufficienti per fornire un mezzo per inserire i valori del membro associabile in un oggetto grafico, o per recuperare i valori fuori dall'oggetto grafico e serializzarli nel modo appropriato. Per fornire questa funzionalità, il `target` gli oggetti nelle firme della funzione di accesso precedente devono essere in grado di archiviare i valori. Il meccanismo di archiviazione deve essere coerenza con il principio di membro associabile che il membro è associabile alle destinazioni in cui il membro associabile non è nell'elenco dei membri. Servizi XAML di .NET framework fornisce una tecnica di implementazione per membro associabile archivi tramite le API <xref:System.Xaml.IAttachedPropertyStore> e <xref:System.Xaml.AttachablePropertyServices>. <xref:System.Xaml.IAttachedPropertyStore> viene usato dai writer XAML per individuare l'implementazione dell'archivio e deve essere implementata nel tipo che è il `target` delle funzioni di accesso. Il metodo statico <xref:System.Xaml.AttachablePropertyServices> API vengono utilizzate all'interno del corpo delle funzioni di accesso e fare riferimento al membro associabile da relativo <xref:System.Xaml.AttachableMemberIdentifier>.  
  
## <a name="xaml-related-clr-attributes"></a>Attributi CLR correlati a XAML  
 Corretta attribuzione di tipi, membri e gli assembly è importante in ordine al report informazioni sul sistema di tipo XAML ai servizi XAML di .NET Framework. Ciò è rilevante se si prevede di tipi per l'uso con i sistemi XAML direttamente basate su servizi XAML di .NET Framework XAML reader e writer XAML, o se si definisce o si usa un framework che usano XAML basato su tali reader XAML e writer XAML.  
  
 Per un elenco di ciascun attributo XAML correlati che sono rilevante per il supporto XAML di tipi personalizzati, vedere [Related attributi CLR per tipi e librerie personalizzati](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md).  
  
## <a name="usage"></a>Utilizzo  
 Utilizzo di tipi personalizzati è necessario che l'autore del markup deve eseguire il mapping di un prefisso per l'assembly e dello spazio dei nomi CLR che contengono il tipo personalizzato. Questa procedura non è documentata in questo argomento.  
  
## <a name="access-level"></a>Livello di accesso  
 XAML fornisce un modo per caricare e creare istanze di tipi che hanno un `internal` livello di accesso. Questa funzionalità viene fornita in modo che il codice utente possa definire tipi personalizzati e quindi creare un'istanza di tali classi dal markup che fa anche parte dell'ambito stesso codice utente.  
  
 Un esempio di WPF è ogni volta che il codice utente definisce una <xref:System.Windows.Controls.UserControl> inteso come un modo per effettuare il refactoring di un comportamento dell'interfaccia utente, ma non come parte di qualsiasi meccanismo di estensione possibili che potrà essere in cui è inclusa la dichiarazione della classe di supporto con `public` livello di accesso. Questo tipo una <xref:System.Windows.Controls.UserControl> possono essere dichiarate con `internal` accedere se il codice sottostante viene compilato nello stesso assembly da cui viene fatto riferimento come un tipo XAML.  
  
 Per un'applicazione che carica XAML con attendibilità totale e utilizza <xref:System.Xaml.XamlObjectWriter>, il caricamento delle classi con `internal` a livello di accesso è sempre abilitato.  
  
 Per un'applicazione che esegue il caricamento di XAML con attendibilità parziale, è possibile controllare le caratteristiche a livello di accesso usando il <xref:System.Xaml.Permissions.XamlAccessLevel> API. Inoltre, i meccanismi di rinvio (ad esempio, il sistema di modelli WPF) devono essere in grado di propagare le autorizzazioni a livello di accesso e conservarli per le valutazioni di fase di esecuzione finale; Questa operazione viene gestita internamente passando il <xref:System.Xaml.Permissions.XamlAccessLevel> informazioni.  
  
### <a name="wpf-implementation"></a>Implementazione di WPF  
 WPF XAML Usa un modello di accesso parzialmente attendibile dove se BAML viene caricato con attendibilità parziale, l'accesso è limitato a <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> per l'assembly che rappresenta l'origine BAML. Per il differimento, WPF utilizza <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> come un meccanismo per passare le informazioni a livello di accesso.  
  
 Nella terminologia di WPF XAML, un *tipo interno* è un tipo definito dall'assembly stesso che include anche il riferimento XAML. Questo tipo può essere mappato mediante uno spazio dei nomi XAML viene deliberatamente omesso assembly = parte di un mapping, ad esempio, `xmlns:local="clr-namespace:WPFApplication1"`.  Se BAML fa riferimento a un tipo interno e che disponga di tipo `internal` accedere al livello, verrà generato un `GeneratedInternalTypeHelper` classe per l'assembly. Se si desidera evitare `GeneratedInternalTypeHelper`, è necessario utilizzare `public` , livello di accesso deve prendere in considerazione la classe rilevante in un assembly separato e rendere tale assembly dipendente.  
  
## <a name="see-also"></a>Vedere anche
- [Attributi CLR correlati a XAML per tipi e librerie personalizzati](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [Servizi XAML](../../../docs/framework/xaml-services/index.md)
