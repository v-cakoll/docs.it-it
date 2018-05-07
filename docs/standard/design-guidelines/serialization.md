---
title: Serialization1
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db06feefdd9697fd53d64bce60ae11c7e74f8c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="serialization"></a>Serializzazione
La serializzazione è il processo di conversione di un oggetto in un formato che può essere facilmente mantenuto o trasportato. Ad esempio, è possibile serializzare un oggetto, trasportarlo su Internet tramite HTTP e viene deserializzato in computer di destinazione.  
  
 .NET Framework offre tre tecnologie di serializzazione principale ottimizzate per vari scenari di serializzazione. Nella tabella seguente vengono elencate tali tecnologie e vengono indicati i principali tipi .NET Framework correlati.  
  
|**Nome di tecnologia**|**Tipi principali**|**Scenari**|  
|-------------------------|--------------------|-------------------|  
|**Serializzazione del contratto dati**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistenza generale<br />Servizi Web<br />JSON|  
|**Serializzazione XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con il controllo completo sulla forma del codice XML|  
|**Serializzazione di runtime (file binario e SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|Servizi remoti .NET|  
  
 **✓ SI** interazione utente sulla serializzazione durante la progettazione di nuovi tipi.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Scelta della tecnologia di serializzazione corretta da supportare  
 **✓ Provare a** il supporto di serializzazione del contratto dati se le istanze del tipo potrebbero dover essere persistenti o utilizzato nei servizi Web.  
  
 **✓ Provare a** che supportano la serializzazione XML anziché o oltre alla serializzazione del contratto dati se è necessario un maggiore controllo sul formato XML che viene generato quando il tipo è serializzato.  
  
 Questo potrebbe essere necessario in alcuni scenari in cui è necessario usare un file XML costruire di interoperabilità che non è supportata dalla serializzazione del contratto dati, ad esempio, per produrre gli attributi XML.  
  
 **✓ Provare a** che supportano la serializzazione di Runtime se le istanze del tipo devono attraversare i limiti di servizi remoti .NET.  
  
 **X evitare** che supporta la serializzazione di Runtime o la serializzazione XML solo per motivi di persistenza generale. Invece essere serializzazione del contratto dati.  
  
## <a name="supporting-data-contract-serialization"></a>Supporto della serializzazione dei contratti dati  
 Tipi possono supportare la serializzazione del contratto dati applicando il <xref:System.Runtime.Serialization.DataContractAttribute> al tipo e il <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri (campi e proprietà) del tipo.  
  
 **✓ Provare a** contrassegnando i membri di dati di tipo pubblico se il tipo può essere utilizzato in attendibilità parziale.  
  
 In attendibilità totale, in grado di serializzare e deserializzare tipi non pubblici e membri i serializzatori di contratto dati, ma solo i membri pubblici possono essere serializzati e deserializzati in attendibilità parziale.  
  
 **✓ SI** implementano un getter e setter per tutte le proprietà che hanno <xref:System.Runtime.Serialization.DataMemberAttribute>. Serializzatori di contratto dati richiedono entrambi i metodi get e set per il tipo essere considerato come serializzabile. (In .NET Framework 3.5 SP1, alcune proprietà di raccolta è può essere solo get.) Se il tipo non verrà utilizzato in condizioni di attendibilità parziale, è possibile che una o entrambe le funzioni di accesso alle proprietà non siano pubbliche.  
  
 **✓ Provare a** utilizzando i callback di serializzazione per l'inizializzazione delle istanze deserializzate.  
  
 Poiché i costruttori non vengono chiamati quando gli oggetti sono deserializzati, (Esistono eccezioni alla regola. I costruttori di raccolte contrassegnati con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> vengono chiamati durante la deserializzazione.) Pertanto, qualsiasi logica che viene eseguita durante la costruzione normale deve essere implementata come uno dei callback di serializzazione.  
  
 `OnDeserializedAttribute` è l'attributo di callback utilizzate più di frequente. Gli altri attributi della famiglia sono <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> e <xref:System.Runtime.Serialization.OnSerializedAttribute>. Tali attributi possono essere utilizzati rispettivamente per contrassegnare callback eseguiti prima della deserializzazione, prima della serializzazione e dopo la serializzazione.  
  
 **✓ CONSIDERARE** utilizzando il <xref:System.Runtime.Serialization.KnownTypeAttribute> per indicare i tipi concreti che devono essere utilizzati quando si deserializza un oggetto complesso grafico.  
  
 **✓ SI** prendere in considerazione la compatibilità con le versioni precedenti e successivi durante la creazione o modifica dei tipi serializzabili.  
  
 Tenere presente che i flussi serializzati di versioni future del tipo possono essere deserializzati nella versione corrente del tipo e viceversa.  
  
 È importante che comprendere che i membri di dati, anche privati e interni, non è possibile cambiare i relativi nomi, tipi o anche l'ordine nelle versioni future del tipo a meno che non particolare attenzione per mantenere il contratto utilizzando parametri espliciti per gli attributi di contratto dati .  
  
 Quando si apportano modifiche ai tipi serializzabili, testare la compatibilità di serializzazione. provando ad esempio a deserializzare la nuova versione in una versione precedente e viceversa.  
  
 **Provare a ✓** implementazione <xref:System.Runtime.Serialization.IExtensibleDataObject> per consentire sequenze di andata e ritorno tra versioni diverse del tipo.  
  
 L'interfaccia consente al serializzatore di verificare che durante le sequenze di andata e ritorno non venga perso alcun dato. Il <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> proprietà viene utilizzata per archiviare i dati dalla versione futura del tipo che è sconosciuto alla versione corrente, e pertanto non può contenere come membri dei propri dati. Quando la versione corrente viene successivamente serializzata e deserializzata in una versione futura, i dati aggiuntivi saranno disponibili nel flusso serializzato.  
  
## <a name="supporting-xml-serialization"></a>Supporto della serializzazione XML  
 Serializzazione del contratto dati è il principale (impostazione predefinita) la tecnologia di serializzazione in .NET Framework, ma esistono scenari di serializzazione che non supporta la serializzazione del contratto dati. ad esempio non consente di controllare completamente la forma del codice XML creato o utilizzato dal serializzatore. Se tale controllo fine è necessaria, la serializzazione XML da utilizzare, ed è necessario progettare i tipi per supportare questa tecnologia di serializzazione.  
  
 **X evitare** progettazione di tipi in modo specifico per la serializzazione XML, a meno che non esista un motivo molto complessa per controllare la forma del codice XML generato. Questa tecnologia è stata sostituita dalla serializzazione dei contratti dati descritta nella sezione precedente.  
  
 **Provare a ✓** implementazione il <xref:System.Xml.Serialization.IXmlSerializable> interfaccia se si desidera un maggiore controllo sulla forma del codice XML serializzato quella offerta applicando gli attributi di serializzazione XML. Due metodi dell'interfaccia, <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> e <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, consentono di controllare completamente il flusso XML serializzato. È inoltre possibile controllare lo schema XML che viene generato per il tipo applicando il `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Supporto della serializzazione di runtime  
 Serializzazione di runtime è una tecnologia utilizzata da .NET Remoting. Se si ritiene che i tipi saranno trasportati usando i servizi remoti .NET, è necessario assicurarsi che supportano la serializzazione di Runtime.  
  
 Il supporto di base per la serializzazione di Runtime può essere fornito tramite l'applicazione di <xref:System.SerializableAttribute>, e scenari più avanzati coinvolgono l'implementazione di un semplice modello serializzabile di Runtime (implementare <xref:System.Runtime.Serialization.ISerializable> e fornire il costruttore di serializzazione).  
  
 **✓ Provare a** che supportano la serializzazione di Runtime se i tipi da utilizzare con i servizi remoti .NET. Ad esempio, il <xref:System.AddIn?displayProperty=nameWithType> dello spazio dei nomi viene utilizzato .NET Remoting e pertanto tutti i tipi scambiati tra `System.AddIn` aggiuntivo necessario supportare la serializzazione di Runtime.  
  
 **✓ Provare a** implementa il Pattern serializzabile di Runtime se si desidera che il controllo completo sul processo di serializzazione. ad esempio se si desidera trasformare i dati quando vengono serializzati o deserializzati.  
  
 Il modello è molto semplice. È sufficiente implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable> e specificare un costruttore speciale utilizzato quando l'oggetto viene deserializzato.  
  
 **✓ SI** rendere il costruttore di serializzazione protetti e fornire due parametri tipizzati e denominati esattamente come illustrato nell'esempio di seguito.  
  
```  
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```  
  
 **✓ SI** implementare il `ISerializable` membri in modo esplicito.  
  
 **✓ SI** applicare una richiesta di collegamento a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementazione. In questo modo si garantisce che solo è considerato completamente attendibile core e il serializzatore Runtime hanno accesso al membro.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
