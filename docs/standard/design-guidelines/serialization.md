---
title: Serialization1
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: bebb27ac-9712-4196-9931-de19fc04dbac
author: KrzysztofCwalina
ms.openlocfilehash: 3e21251710a44764bd06fbce83f97288b6925bc2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155106"
---
# <a name="serialization"></a>Serializzazione
La serializzazione è il processo di conversione di un oggetto in un formato che può essere facilmente mantenuto o trasportato. Ad esempio, è possibile serializzare un oggetto, trasferirlo via Internet tramite HTTP e deserializzato, il computer di destinazione.  
  
 .NET Framework sono disponibili tre tecnologie di serializzazione principali ottimizzate per vari scenari di serializzazione. Nella tabella seguente vengono elencate tali tecnologie e vengono indicati i principali tipi .NET Framework correlati.  
  
|**Nome della tecnologia**|**Tipi principali**|**Scenari**|  
|-------------------------|--------------------|-------------------|  
|**Serializzazione dei contratti dati**|<xref:System.Runtime.Serialization.DataContractAttribute> <br /> <xref:System.Runtime.Serialization.DataMemberAttribute> <br /> <xref:System.Runtime.Serialization.DataContractSerializer> <br /> <xref:System.Runtime.Serialization.NetDataContractSerializer> <br /> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <br /> <xref:System.Runtime.Serialization.ISerializable>|Persistenza generale<br />Servizi Web<br />JSON|  
|**Serializzazione XML**|<xref:System.Xml.Serialization.XmlSerializer>|Formato XML con il controllo completo sulla forma del codice XML|  
|**Serializzazione di runtime (binaria e SOAP)**|<xref:System.SerializableAttribute> <br /> <xref:System.Runtime.Serialization.ISerializable> <br /> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <br /> <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>|Servizi remoti .NET|  
  
 **✓ DO** interazione utente sulla serializzazione durante la progettazione di nuovi tipi.  
  
## <a name="choosing-the-right-serialization-technology-to-support"></a>Scelta della tecnologia di serializzazione corretta da supportare  
 **✓ CONSIDER** il supporto di serializzazione del contratto dati se le istanze del tipo potrebbero dover essere persistenti o utilizzato nei servizi Web.  
  
 **✓ CONSIDER** che supportano la serializzazione XML anziché o oltre alla serializzazione del contratto dati se è necessario un maggiore controllo sul formato XML che viene generato quando il tipo è serializzato.  
  
 Ciò potrebbe essere necessario in alcuni scenari in cui è necessario usare un file XML costruire l'interoperabilità non supportato dalla serializzazione dei contratti dati, ad esempio, per produrre gli attributi XML.  
  
 **✓ CONSIDER** che supportano la serializzazione di Runtime se le istanze del tipo devono attraversare i limiti di servizi remoti .NET.  
  
 **X AVOID** che supporta la serializzazione di Runtime o la serializzazione XML solo per motivi di persistenza generale. Preferisce invece della serializzazione dei contratti dati.  
  
## <a name="supporting-data-contract-serialization"></a>Supporto della serializzazione dei contratti dati  
 I tipi supportino la serializzazione del contratto dati applicando il <xref:System.Runtime.Serialization.DataContractAttribute> al tipo e il <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri (campi e proprietà) del tipo.  
  
 **✓ CONSIDER** contrassegnando i membri di dati di tipo pubblico se il tipo può essere utilizzato in attendibilità parziale.  
  
 In attendibilità totale, i serializzatori dei contratti dati possono serializzare e deserializzare i tipi non pubblici e membri, ma solo i membri pubblici possono essere serializzati e deserializzati in attendibilità parziale.  
  
 **✓ DO** implementano un getter e setter per tutte le proprietà che hanno <xref:System.Runtime.Serialization.DataMemberAttribute>. Serializzatori dei contratti dati richiedono entrambi il getter e setter per il tipo possa essere considerato serializzabile. (In .NET Framework 3.5 SP1, alcune proprietà di raccolta può essere solo get). Se il tipo non verrà utilizzato in condizioni di attendibilità parziale, è possibile che una o entrambe le funzioni di accesso alle proprietà non siano pubbliche.  
  
 **✓ CONSIDER** utilizzando i callback di serializzazione per l'inizializzazione delle istanze deserializzate.  
  
 Poiché i costruttori non vengono chiamati quando gli oggetti sono deserializzati, (Sono presenti eccezioni alla regola. I costruttori di raccolte contrassegnati con <xref:System.Runtime.Serialization.CollectionDataContractAttribute> vengono chiamati durante la deserializzazione.) Pertanto, qualsiasi logica eseguita durante la costruzione normale deve essere implementata come uno dei callback di serializzazione.  
  
 `OnDeserializedAttribute` è l'attributo di callback più comunemente utilizzato. Gli altri attributi della famiglia sono <xref:System.Runtime.Serialization.OnDeserializingAttribute>, <xref:System.Runtime.Serialization.OnSerializingAttribute> e <xref:System.Runtime.Serialization.OnSerializedAttribute>. Tali attributi possono essere utilizzati rispettivamente per contrassegnare callback eseguiti prima della deserializzazione, prima della serializzazione e dopo la serializzazione.  
  
 **✓ CONSIDER** utilizzando il <xref:System.Runtime.Serialization.KnownTypeAttribute> per indicare i tipi concreti che devono essere utilizzati quando si deserializza un oggetto complesso grafico.  
  
 **✓ DO** prendere in considerazione la compatibilità con le versioni precedenti e successivi durante la creazione o modifica dei tipi serializzabili.  
  
 Tenere presente che i flussi serializzati di versioni future del tipo possono essere deserializzati nella versione corrente del tipo e viceversa.  
  
 È importante che comprendere che i membri dati, anche privati e interni, non è possibile modificare i relativi nomi, tipi o l'ordine nelle versioni future del tipo a meno che non è necessario prestare attenzione speciale per mantenere il contratto utilizzando parametri espliciti per gli attributi del contratto dati .  
  
 Quando si apportano modifiche ai tipi serializzabili, testare la compatibilità della serializzazione. provando ad esempio a deserializzare la nuova versione in una versione precedente e viceversa.  
  
 **✓ CONSIDER** implementazione <xref:System.Runtime.Serialization.IExtensibleDataObject> per consentire sequenze di andata e ritorno tra versioni diverse del tipo.  
  
 L'interfaccia consente al serializzatore di verificare che durante le sequenze di andata e ritorno non venga perso alcun dato. Il <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A?displayProperty=nameWithType> proprietà viene utilizzata per archiviare i dati della versione futura del tipo che è sconosciuto alla versione corrente, e pertanto non può contenere membri dei propri dati. Quando la versione corrente viene successivamente serializzata e deserializzata in una versione futura, i dati aggiuntivi saranno disponibili nel flusso serializzato.  
  
## <a name="supporting-xml-serialization"></a>Supporto della serializzazione XML  
 Serializzazione del contratto dati è il principale (predefinita) la tecnologia di serializzazione in .NET Framework, ma esistono gli scenari di serializzazione che non supporta la serializzazione del contratto dati. ad esempio non consente di controllare completamente la forma del codice XML creato o utilizzato dal serializzatore. Se è necessario un controllo così accurato, la serializzazione XML da utilizzare, ed è necessario progettare i tipi per supportare questa tecnologia di serializzazione.  
  
 **X AVOID** progettazione di tipi in modo specifico per la serializzazione XML, a meno che non esista un motivo molto complessa per controllare la forma del codice XML generato. Questa tecnologia è stata sostituita dalla serializzazione dei contratti dati descritta nella sezione precedente.  
  
 **✓ CONSIDER** implementazione il <xref:System.Xml.Serialization.IXmlSerializable> interfaccia se si desidera un maggiore controllo sulla forma del codice XML serializzato quella offerta applicando gli attributi di serializzazione XML. Due metodi per l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> e <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>, consentono di controllare completamente il flusso XML serializzato. È inoltre possibile controllare lo schema XML generato per il tipo applicando il `XmlSchemaProviderAttribute`.  
  
## <a name="supporting-runtime-serialization"></a>Supporto della serializzazione di runtime  
 Serializzazione di runtime è una tecnologia utilizzata dai servizi remoti .NET. Se si ritiene che i tipi verranno trasportati utilizzando i servizi remoti .NET, è necessario verificare che supportino la serializzazione di Runtime.  
  
 Il supporto di base per la serializzazione di Runtime può essere fornito applicando il <xref:System.SerializableAttribute>, e gli scenari più avanzati prevedono l'implementazione di un semplice modello di Runtime serializzabile (implementa <xref:System.Runtime.Serialization.ISerializable> e specifica il costruttore di serializzazione).  
  
 **✓ CONSIDER** che supportano la serializzazione di Runtime se i tipi da utilizzare con i servizi remoti .NET. Ad esempio, il <xref:System.AddIn?displayProperty=nameWithType> dello spazio dei nomi Usa servizi remoti .NET e pertanto tutti i tipi scambiati tra `System.AddIn` componenti aggiuntivi necessari per supportare la serializzazione di Runtime.  
  
 **✓ CONSIDER** implementa il Pattern serializzabile di Runtime se si desidera che il controllo completo sul processo di serializzazione. ad esempio se si desidera trasformare i dati quando vengono serializzati o deserializzati.  
  
 Il modello è molto semplice. È sufficiente implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable> e specificare un costruttore speciale utilizzato quando l'oggetto viene deserializzato.  
  
 **✓ DO** rendere il costruttore di serializzazione protetti e fornire due parametri tipizzati e denominati esattamente come illustrato nell'esempio di seguito.  
  
```csharp
[Serializable]  
public class Person : ISerializable {  
    protected Person(SerializationInfo info, StreamingContext context) {  
        ...  
    }  
}  
```
  
 **✓ DO** implementare il `ISerializable` membri in modo esplicito.  
  
 **✓ DO** applicare una richiesta di collegamento a <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> implementazione. Ciò garantisce che solo è considerato completamente attendibile core e il serializzatore di Runtime hanno accesso al membro.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
