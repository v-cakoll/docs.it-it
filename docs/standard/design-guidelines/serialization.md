---
title: Serializzazione
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
ms.openlocfilehash: d07549da371e403adca089c601ee5b028b268086
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291682"
---
# <a name="serialization"></a>Serializzazione
La serializzazione è il processo di conversione di un oggetto in un formato che può essere reso immediatamente permanente o trasportato. Ad esempio, è possibile serializzare un oggetto, trasportarlo su Internet tramite HTTP e deserializzarlo nel computer di destinazione.

 Il .NET Framework offre tre tecnologie di serializzazione principali ottimizzate per vari scenari di serializzazione. Nella tabella seguente vengono elencate tali tecnologie e vengono indicati i principali tipi .NET Framework correlati.

|**Nome tecnologia**|**Tipi principali**|**Scenari**|
|-------------------------|--------------------|-------------------|
|**Serializzazione dei contratti dati**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistenza generale<br />Servizi Web<br />JSON|
|**Serializzazione XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con controllo completo sulla forma del codice XML|
|**Serializzazione runtime (binario e SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|Servizi remoti .NET|

 ✔️ considerare la serializzazione quando si progettano nuovi tipi.

## <a name="choosing-the-right-serialization-technology-to-support"></a>Scelta della tecnologia di serializzazione corretta da supportare
 ✔️ CONSIGLIABILE supportare la serializzazione del contratto dati se è possibile che le istanze del tipo debbano essere rese permanente o utilizzate nei servizi Web.

 ✔️ CONSIGLIABILE supportare la serializzazione XML anziché o in aggiunta alla serializzazione del contratto dati se è necessario un maggiore controllo sul formato XML generato quando il tipo viene serializzato.

 Questa operazione può essere necessaria in alcuni scenari di interoperabilità in cui è necessario usare un costrutto XML non supportato dalla serializzazione del contratto dati, ad esempio per produrre attributi XML.

 ✔️ CONSIGLIABILE supportare la serializzazione di runtime se le istanze del tipo devono spostarsi tra i limiti .NET Remoting.

 ❌EVITARE il supporto della serializzazione di runtime o della serializzazione XML solo per motivi di persistenza generale. Preferisco invece la serializzazione del contratto dati.

## <a name="supporting-data-contract-serialization"></a>Supporto della serializzazione dei contratti dati
 I tipi possono supportare la serializzazione del contratto dati applicando al <xref:System.Runtime.Serialization.DataContractAttribute> tipo e ai <xref:System.Runtime.Serialization.DataMemberAttribute> membri (campi e proprietà) del tipo.

 ✔️ PROVARE a contrassegnare i membri dati del tipo Public se il tipo può essere usato in attendibilità parziale.

 Nell'attendibilità totale, i serializzatori dei contratti dati possono serializzare e deserializzare i tipi e i membri non pubblici, ma solo i membri pubblici possono essere serializzati e deserializzati in attendibilità parziale.

 ✔️ implementano un getter e un setter in tutte le proprietà di <xref:System.Runtime.Serialization.DataMemberAttribute> . Per essere considerati serializzabili, i serializzatori dei contratti dati richiedono sia il getter che il setter per il tipo. In .NET Framework 3,5 SP1 alcune proprietà della raccolta possono essere solo Get. Se il tipo non verrà usato in attendibilità parziale, una o entrambe le funzioni di accesso alle proprietà possono essere non pubbliche.

 ✔️ CONSIGLIABILE utilizzare i callback di serializzazione per l'inizializzazione di istanze deserializzate.

 Poiché i costruttori non vengono chiamati quando gli oggetti sono deserializzati, Sono presenti eccezioni alla regola. I costruttori di raccolte contrassegnate con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> vengono chiamati durante la deserializzazione. Pertanto, qualsiasi logica eseguita durante la costruzione normale deve essere implementata come uno dei callback di serializzazione.

 `OnDeserializedAttribute`è l'attributo di callback usato più di frequente. Gli altri attributi della famiglia sono <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> e <xref:System.Runtime.Serialization.OnSerializedAttribute>. Tali attributi possono essere utilizzati rispettivamente per contrassegnare callback eseguiti prima della deserializzazione, prima della serializzazione e dopo la serializzazione.

 ✔️ CONSIGLIABILE utilizzare <xref:System.Runtime.Serialization.KnownTypeAttribute> per indicare tipi concreti che devono essere utilizzati durante la deserializzazione di un oggetto grafico complesso.

 ✔️ prendere in considerazione la compatibilità con le versioni precedenti e precedenti quando si creano o modificano tipi serializzabili.

 Tenere presente che i flussi serializzati di versioni future del tipo possono essere deserializzati nella versione corrente del tipo e viceversa.

 Assicurarsi di aver compreso che i membri dati, anche privati e interni, non possono modificare i nomi, i tipi o anche il proprio ordine nelle versioni future del tipo, a meno che non si debba prestare particolare attenzione a mantenere il contratto usando parametri espliciti per gli attributi del contratto dati.

 Testare la compatibilità della serializzazione quando si apportano modifiche ai tipi serializzabili. provando ad esempio a deserializzare la nuova versione in una versione precedente e viceversa.

 ✔️ prendere in considerazione l'implementazione <xref:System.Runtime.Serialization.IExtensibleDataObject> di per consentire l'esecuzione di sequenze di andata e ritorno tra versioni diverse del tipo.

 L'interfaccia consente al serializzatore di verificare che durante le sequenze di andata e ritorno non venga perso alcun dato. La <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> proprietà viene utilizzata per archiviare i dati della versione futura del tipo sconosciuto alla versione corrente, quindi non può archiviarla nei relativi membri dati. Quando la versione corrente viene successivamente serializzata e deserializzata in una versione futura, i dati aggiuntivi saranno disponibili nel flusso serializzato.

## <a name="supporting-xml-serialization"></a>Supporto della serializzazione XML
 La serializzazione del contratto dati è la tecnologia di serializzazione principale (predefinita) nell'.NET Framework, ma sono presenti scenari di serializzazione non supportati dalla serializzazione del contratto dati. ad esempio non consente di controllare completamente la forma del codice XML creato o utilizzato dal serializzatore. Se è necessario un controllo così accurato, è necessario utilizzare la serializzazione XML ed è necessario progettare i tipi per supportare questa tecnologia di serializzazione.

 ❌EVITARE di progettare i tipi in modo specifico per la serializzazione XML, a meno che non esista un motivo molto forte per controllare la forma del codice XML prodotto. Questa tecnologia è stata sostituita dalla serializzazione dei contratti dati descritta nella sezione precedente.

 ✔️ prendere in considerazione l'implementazione dell' <xref:System.Xml.Serialization.IXmlSerializable> interfaccia se si desidera un maggiore controllo sulla forma del codice XML serializzato rispetto a quello offerto applicando gli attributi di serializzazione XML. Due metodi dell'interfaccia, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> e <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> , consentono di controllare completamente il flusso XML serializzato. È inoltre possibile controllare la XML Schema generata per il tipo applicando `XmlSchemaProviderAttribute` .

## <a name="supporting-runtime-serialization"></a>Supporto della serializzazione di runtime
 La serializzazione di runtime è una tecnologia utilizzata dalla comunicazione remota di .NET. Se si ritiene che i tipi vengano trasportati tramite .NET Remoting, è necessario assicurarsi che supportino la serializzazione di Runtime.

 Il supporto di base per la serializzazione di runtime può essere fornito applicando e <xref:System.SerializableAttribute> scenari più avanzati implicano l'implementazione di un modello serializzabile di runtime semplice (implementare <xref:System.Runtime.Serialization.ISerializable> e fornire il costruttore di serializzazione).

 ✔️ CONSIGLIABILE supportare la serializzazione di runtime se i tipi verranno utilizzati con .NET Remoting. Lo <xref:System.AddIn?displayProperty=nameWithType> spazio dei nomi, ad esempio, utilizza .NET Remoting, pertanto tutti i tipi scambiati tra i `System.AddIn` componenti aggiuntivi devono supportare la serializzazione di Runtime.

 ✔️ CONSIGLIABILE implementare il modello di runtime serializzabile se si desidera il controllo completo sul processo di serializzazione. ad esempio se si desidera trasformare i dati quando vengono serializzati o deserializzati.

 Il modello è molto semplice. È sufficiente implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable> e specificare un costruttore speciale utilizzato quando l'oggetto viene deserializzato.

 ✔️ rendere protetto il costruttore di serializzazione e fornire due parametri digitati e denominati esattamente come illustrato nell'esempio qui.

```csharp
[Serializable]
public class Person : ISerializable
{
    protected Person(SerializationInfo info, StreamingContext context)
    {
        // ...
    }
}
```

 ✔️ implementano i <xref:System.Runtime.Serialization.ISerializable> membri in modo esplicito.

 ✔️ applicare una richiesta di collegamento all' <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementazione. In questo modo si garantisce che solo i core completamente attendibili e il serializzatore di Runtime abbiano accesso al membro.

 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](index.md)
- [Linee guida sull'utilizzo](usage-guidelines.md)
