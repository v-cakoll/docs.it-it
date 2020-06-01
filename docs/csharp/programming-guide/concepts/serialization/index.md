---
title: Serializzazione (C#)
ms.date: 01/02/2020
ms.openlocfilehash: b2532ccf281fdfaa951d56675066f1e239f9f480
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241981"
---
# <a name="serialization-c"></a>Serializzazione (C#)

Il termine serializzazione indica il processo di conversione di un oggetto in un flusso di byte, allo scopo di archiviare tale oggetto o trasmetterlo alla memoria, a un database o a un file. Il fine principale della serializzazione è salvare lo stato di un oggetto per consentirne la ricreazione in caso di necessità. Il processo inverso è denominato deserializzazione.

## <a name="how-serialization-works"></a>Funzionamento della serializzazione

La figura seguente illustra il processo complessivo di serializzazione:

![Rappresentazione grafica della serializzazione](./media/index/serialization-process.gif)

L'oggetto viene serializzato in un flusso che contiene i dati. Il flusso può inoltre contenere informazioni sul tipo dell'oggetto, ad esempio la versione, le impostazioni cultura e il nome dell'assembly. Da tale flusso, l'oggetto può essere archiviato in un database, un file o una memoria.

### <a name="uses-for-serialization"></a>Usi della serializzazione

La serializzazione consente allo sviluppatore di salvare lo stato di un oggetto e di ricrearlo in base alle esigenze, fornendo l'archiviazione di oggetti, nonché lo scambio di dati. Tramite la serializzazione, uno sviluppatore può eseguire azioni come le seguenti:

* Invio dell'oggetto a un'applicazione remota tramite un servizio Web
* Passaggio di un oggetto da un dominio a un altro
* Passaggio di un oggetto tramite un firewall come stringa JSON o XML
* Gestione della sicurezza o delle informazioni specifiche dell'utente tra le applicazioni

## <a name="json-serialization"></a>Serializzazione JSON

Lo <xref:System.Text.Json> spazio dei nomi contiene classi per la serializzazione e la deserializzazione di JavaScript Object Notation (JSON). JSON è uno standard aperto comunemente usato per la condivisione di dati sul Web.

La serializzazione JSON serializza le proprietà pubbliche di un oggetto in una stringa, una matrice di byte o un flusso conforme alla [specifica JSON RFC 8259](https://tools.ietf.org/html/rfc8259). Per controllare la modalità <xref:System.Text.Json.JsonSerializer> di serializzazione o deserializzazione di un'istanza della classe:

* Usare un <xref:System.Text.Json.JsonSerializerOptions> oggetto
* Applicare gli attributi dallo <xref:System.Text.Json.Serialization> spazio dei nomi alle classi o alle proprietà
* [Implementare convertitori personalizzati](../../../../standard/serialization/system-text-json-converters-how-to.md)

## <a name="binary-and-xml-serialization"></a>Serializzazione in formato binario e XML

Lo <xref:System.Runtime.Serialization> spazio dei nomi contiene classi per la serializzazione e la deserializzazione binaria e XML.

La serializzazione binaria usa la codifica binaria per generare una serializzazione compatta per usi quali l'archiviazione o i flussi di rete basati sui socket. Nella serializzazione binaria vengono serializzati tutti i membri, anche quelli di sola lettura, e le prestazioni risultano migliorate.

La serializzazione XML serializza le proprietà e i campi pubblici di un oggetto, o i parametri e i valori restituiti dei metodi, in un flusso XML conforme a uno specifico documento in linguaggio XSD (XML Schema Definition). La serializzazione XML genera classi fortemente tipizzate con proprietà e campi pubblici convertiti in XML. <xref:System.Xml.Serialization>contiene classi per la serializzazione e la deserializzazione di XML. È possibile applicare attributi alle classi e ai membri delle classi per controllare il modo in cui <xref:System.Xml.Serialization.XmlSerializer> serializza o deserializza un'istanza della classe.

### <a name="making-an-object-serializable"></a>Rendere un oggetto serializzabile

Per la serializzazione binaria o XML, è necessario:

* Oggetto da serializzare.
* Flusso che deve contenere l'oggetto serializzato
* <xref:System.Runtime.Serialization.Formatter?displayProperty=fullName>Istanza di

Applicare l' <xref:System.SerializableAttribute> attributo a un tipo per indicare che le istanze del tipo possono essere serializzate. Se si prova a serializzare ma il tipo non ha l'attributo <xref:System.SerializableAttribute> viene generata un'eccezione.

Per evitare che un campo venga serializzato, applicare l' <xref:System.NonSerializedAttribute> attributo. Se un campo di un tipo serializzabile contiene un puntatore, un handle o un'altra struttura di dati specifica di un particolare ambiente e tale campo non può essere ricostituito in modo corretto in un ambiente diverso, è necessario renderlo non serializzabile.

Se una classe serializzata contiene riferimenti a oggetti di altre classi contrassegnate con <xref:System.SerializableAttribute>, verranno serializzati anche tali oggetti.

### <a name="basic-and-custom-serialization"></a>Serializzazione di base e personalizzata

La serializzazione binaria e XML può essere eseguita in due modi: Basic e Custom.

La serializzazione di base USA .NET per serializzare automaticamente l'oggetto. L'unico requisito è che alla classe sia <xref:System.SerializableAttribute> applicato l'attributo. È possibile usare l'attributo <xref:System.NonSerializedAttribute> per evitare la serializzazione di campi specifici.

Quando si usa la serializzazione di base, il controllo delle versioni degli oggetti può creare problemi. Usare la serializzazione personalizzata quando gli aspetti di controllo delle versioni sono importanti. La serializzazione di base è il modo più semplice per eseguire la serializzazione, ma non assicura il controllo completo del processo.

Con la serializzazione personalizzata è possibile specificare esattamente quali oggetti verranno serializzati e il modo in cui verrà eseguita la serializzazione. La classe deve essere contrassegnata con <xref:System.SerializableAttribute> e implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable>. Se si desidera che l'oggetto venga deserializzato anche in modo personalizzato, utilizzare un costruttore personalizzato.

## <a name="designer-serialization"></a>Serializzazione della finestra di progettazione

La serializzazione della finestra di progettazione è una forma speciale di serializzazione che interessa il tipo di persistenza dell'oggetto associato agli strumenti di sviluppo. La serializzazione della finestra di progettazione è il processo di conversione di un oggetto grafico in un file di origine che può essere usato in seguito per recuperare l'oggetto grafico stesso. Un file di origine può contenere codice, markup o anche informazioni su tabelle SQL.

## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> Argomenti correlati ed esempi  

[Panoramica di System. Text. JSON](../../../../standard/serialization/system-text-json-overview.md) Viene illustrato come ottenere la `System.Text.Json` libreria.

[Come serializzare e deserializzare JSON in .NET](../../../../standard/serialization/system-text-json-how-to.md).
Viene illustrato come leggere e scrivere dati oggetto da e verso JSON usando la <xref:System.Text.Json.JsonSerializer> classe.

[Procedura dettagliata: Persistenza di un oggetto in Visual Studio (C#)](walkthrough-persisting-an-object-in-visual-studio.md)  
Dimostra in che modo è possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.

[Come leggere i dati di un oggetto da un file XML (C#)](how-to-read-object-data-from-an-xml-file.md)  
Spiega come leggere i dati della classe precedentemente scritti in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.

[Come scrivere i dati di un oggetto in un file XML (C#)](how-to-write-object-data-to-an-xml-file.md)  
Spiega come scrivere l'oggetto da una classe in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.
