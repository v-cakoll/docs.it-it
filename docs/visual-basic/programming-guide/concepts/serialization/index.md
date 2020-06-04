---
title: Serializzazione
ms.date: 07/20/2015
ms.assetid: 67379a76-5465-4af8-a781-0b0b25a62d9a
ms.openlocfilehash: db14147a23940fa2403613036750be1bca566e8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413142"
---
# <a name="serialization-visual-basic"></a>Serializzazione (Visual Basic)
Il termine serializzazione indica il processo di conversione di un oggetto in un flusso di byte allo scopo di archiviare tale oggetto o trasmetterlo alla memoria, a un database o a un file. Il fine principale della serializzazione è salvare lo stato di un oggetto per consentirne la ricreazione in caso di necessità. Il processo inverso è denominato deserializzazione.  
  
## <a name="how-serialization-works"></a>Funzionamento della serializzazione  
 La figura seguente illustra il processo complessivo di serializzazione.  
  
![Rappresentazione grafica della serializzazione](./media/index/serialization-process.gif)
  
 L'oggetto viene serializzato in un flusso che contiene non solo i dati, ma anche informazioni sul tipo di oggetto, ad esempio la versione, le impostazioni cultura e il nome dell'assembly. Da questo flusso è possibile archiviare l'oggetto in un database, in un file oppure nella memoria.  
  
### <a name="uses-for-serialization"></a>Usi della serializzazione  
 La serializzazione consente allo sviluppatore di salvare lo stato di un oggetto per ricrearlo quando necessario, consentendo sia l'archiviazione di oggetti sia lo scambio di dati. Grazie alla serializzazione, uno sviluppatore può eseguire azioni quali l'invio dell'oggetto a un'applicazione remota tramite un servizio Web, il passaggio di un oggetto da un dominio a un altro, il passaggio di un oggetto attraverso un firewall come stringa XML o la gestione su diverse applicazioni di informazioni sulla sicurezza o specifiche dell'utente.  
  
### <a name="making-an-object-serializable"></a>Rendere un oggetto serializzabile  
 Per serializzare un oggetto, sono necessari l'oggetto da serializzare, un flusso che contenga l'oggetto serializzato e un <xref:System.Runtime.Serialization.Formatter>. <xref:System.Runtime.Serialization> contiene classi necessarie per la serializzazione e la deserializzazione di oggetti.  
  
 Applicare l'attributo <xref:System.SerializableAttribute> a un tipo per indicare che le istanze di tale tipo possono essere serializzate. Viene generata un'eccezione <xref:System.Runtime.Serialization.SerializationException> se si tenta di serializzare ma il tipo non ha l'attributo <xref:System.SerializableAttribute>.  
  
 Se si vuole evitare che un campo della classe venga serializzato, applicare l'attributo <xref:System.NonSerializedAttribute>. Se un campo di un tipo serializzabile contiene un puntatore, un handle o un'altra struttura di dati specifica di un particolare ambiente e tale campo non può essere ricostituito in modo corretto in un ambiente diverso, è necessario renderlo non serializzabile.  
  
 Se una classe serializzata contiene riferimenti a oggetti di altre classi contrassegnate con <xref:System.SerializableAttribute>, verranno serializzati anche tali oggetti.  
  
## <a name="binary-and-xml-serialization"></a>Serializzazione in formato binario e XML  
 È possibile usare la serializzazione in formato binario o XML. Nella serializzazione binaria vengono serializzati tutti i membri, anche quelli di sola lettura, e le prestazioni risultano migliorate. La serializzazione XML offre codice più leggibile nonché una maggiore flessibilità nella condivisione e nell'uso degli oggetti per scopi di interoperabilità.  
  
### <a name="binary-serialization"></a>Serializzazione binaria  
 La serializzazione binaria usa la codifica binaria per generare una serializzazione compatta per usi quali l'archiviazione o i flussi di rete basati sui socket.  
  
### <a name="xml-serialization"></a>Serializzazione XML  
 La serializzazione XML serializza le proprietà e i campi pubblici di un oggetto, o i parametri e i valori restituiti dei metodi, in un flusso XML conforme a uno specifico documento in linguaggio XSD (XML Schema Definition). La serializzazione XML genera classi fortemente tipizzate con proprietà e campi pubblici convertiti in XML. <xref:System.Xml.Serialization> contiene le classi necessarie per la serializzazione e la deserializzazione XML.  
  
 È possibile applicare attributi alle classi e ai membri delle classi per controllare il modo in cui <xref:System.Xml.Serialization.XmlSerializer> serializza o deserializza un'istanza della classe.  
  
## <a name="basic-and-custom-serialization"></a>Serializzazione di base e personalizzata  
 La serializzazione può essere eseguita secondo due modalità: di base e personalizzata. La serializzazione di base usa .NET Framework per serializzare l'oggetto in modo automatico.  
  
### <a name="basic-serialization"></a>Serializzazione di base  
 L'unico requisito della serializzazione di base è che all'oggetto sia applicato l'attributo <xref:System.SerializableAttribute>. È possibile usare l'attributo <xref:System.NonSerializedAttribute> per evitare la serializzazione di campi specifici.  
  
 Quando si usa la serializzazione di base, è possibile che il controllo delle versioni degli oggetti crei problemi. In questo caso, può essere preferibile la serializzazione personalizzata. La serializzazione di base è il modo più semplice per eseguire la serializzazione, ma non assicura il controllo completo del processo.  
  
### <a name="custom-serialization"></a>Serializzazione personalizzata  
 Con la serializzazione personalizzata è possibile specificare esattamente quali oggetti verranno serializzati e il modo in cui verrà eseguita la serializzazione. La classe deve essere contrassegnata con <xref:System.SerializableAttribute> e implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
 Se si vuole che un oggetto venga anche deserializzato in modo personalizzato, è necessario usare un costruttore personalizzato.  
  
## <a name="designer-serialization"></a>Serializzazione della finestra di progettazione  
 La serializzazione della finestra di progettazione è una forma speciale di serializzazione che interessa il tipo di persistenza dell'oggetto solitamente associato agli strumenti di sviluppo. La serializzazione della finestra di progettazione è il processo di conversione di un oggetto grafico in un file di origine che può essere usato in seguito per recuperare l'oggetto grafico stesso. Un file di origine può contenere codice, markup o anche informazioni su tabelle SQL.  
  
## <a name="related-topics-and-examples"></a><a name="BKMK_RelatedTopics"></a> Argomenti correlati ed esempi  
 [Procedura dettagliata: Persistenza di un oggetto in Visual Studio (Visual Basic)](walkthrough-persisting-an-object-in-visual-studio.md)  
 Dimostra in che modo è possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.  
  
 [Procedura: Leggere dati oggetto in un file XML (Visual Basic)](how-to-read-object-data-from-an-xml-file.md)  
 Spiega come leggere i dati della classe precedentemente scritti in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.  
  
 [Procedura: Scrivere dati oggetto in un file XML (Visual Basic)](how-to-write-object-data-to-an-xml-file.md)  
 Spiega come scrivere l'oggetto da una classe in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.
