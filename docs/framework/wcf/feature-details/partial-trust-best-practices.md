---
title: Procedure consigliate in ambienti parzialmente attendibili
ms.date: 03/30/2017
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
ms.openlocfilehash: 7d5bcc7f9f179553188b4ce90c724dc0bd839670
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663027"
---
# <a name="partial-trust-best-practices"></a>Procedure consigliate in ambienti parzialmente attendibili

In questo argomento descrive le procedure consigliate durante l'esecuzione di Windows Communication Foundation (WCF) in un ambiente parzialmente attendibile.

## <a name="serialization"></a>Serializzazione

Applicare le procedure seguenti quando si utilizza <xref:System.Runtime.Serialization.DataContractSerializer> in un'applicazione parzialmente attendibile.

- Tutti i tipi serializzabili devono essere contrassegnati in modo esplicito con l'attributo `[DataContract]`. Le tecniche seguenti non sono supportate in un ambiente parzialmente attendibile:

- Contrassegno delle classi da serializzare con <xref:System.SerializableAttribute>.

- Implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable> per consentire a una classe di controllare il suo processo di serializzazione.

### <a name="using-datacontractserializer"></a>Utilizzo di DataContractSerializer

- Tutti i tipi contrassegnati con l'attributo `[DataContract]` devono essere pubblici. Impossibile serializzare tipi non pubblici in un ambiente parzialmente attendibile.

- I membri `[DataContract]` in un tipo `[DataContract]` serializzabile devono essere pubblici. Un tipo con un `[DataMember]` non pubblico non può essere serializzato in un ambiente parzialmente attendibile.

- I metodi che gestiscono eventi di serializzazione (ad esempio `OnSerializing`, `OnSerialized`, `OnDeserializing` e `OnDeserialized`) devono essere dichiarati pubblici. Sono tuttavia supportate le implementazioni sia esplicite che implicite di <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29>.

- I tipi `[DataContract]` implementati in assembly contrassegnati con <xref:System.Security.AllowPartiallyTrustedCallersAttribute> non devono eseguire azioni correlate alla protezione nel costruttore del tipo, poiché <xref:System.Runtime.Serialization.DataContractSerializer> non chiama il costruttore dell'oggetto di cui è appena stata creata un'istanza durante la deserializzazione. In particolare, è necessario evitare le tecniche di sicurezza comuni seguenti per i tipi `[DataContract]`:

- Tentare di limitare l'accesso parzialmente attendibile rendendo interno o privato il costruttore del tipo.

- Limitare l'accesso al tipo aggiungendo un `[LinkDemand]` al costruttore del tipo.

- Dare per scontato che, dato che l'istanza dell'oggetto è stata creata correttamente, qualsiasi controllo di convalida applicato dal costruttore abbia avuto esito positivo.

### <a name="using-ixmlserializable"></a>Utilizzo di IXmlSerializable

Le procedure consigliate seguenti si applicano ai tipi che implementano <xref:System.Xml.Serialization.IXmlSerializable> e che vengono serializzati tramite <xref:System.Runtime.Serialization.DataContractSerializer>:

- Le implementazioni del metodo statico <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> devono essere `public`.

- I metodi di istanza che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> devono essere `public`.

## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>Utilizzo di WCF da codice della piattaforma completamente attendibile che consente chiamate da chiamanti parzialmente attendibili

Il modello di sicurezza parzialmente attendibile WCF si presuppone che qualsiasi chiamante di una proprietà o un metodo pubblico di WCF è in esecuzione nel contesto di sicurezza dall'accesso codice dell'applicazione host. WCF si presuppone inoltre tale contesto di sicurezza solo un'applicazione disponibile per ogni <xref:System.AppDomain>, e che questo contesto viene stabilito a <xref:System.AppDomain> ora di creazione da un host attendibile (ad esempio, da una chiamata a <xref:System.AppDomain.CreateDomain%2A> o da Gestione applicazioni ASP.NET).

Questo modello di sicurezza si applica alle applicazioni scritte dall'utente che non possono richiedere autorizzazioni CAS aggiuntive, ad esempio codice utente in esecuzione in un'applicazione ASP.NET con un livello di attendibilità medio. Tuttavia, il codice di piattaforma completamente attendibile (ad esempio, un assembly di terze parti che viene installato nella global assembly cache e accetta le chiamate da codice parzialmente attendibile) occorre fare esplicitamente attenzione quando si chiama per conto di un'applicazione parzialmente attendibile in WCF evitare di introdurre vulnerabilità di sicurezza a livello di applicazione.

Codice di attendibilità totale deve evitare di modificare l'autorizzazione CAS impostata del thread corrente (chiamando <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, o <xref:System.Security.PermissionSet.Deny%2A>) prima di chiamare le API WCF per conto di codice parzialmente attendibile. L'asserzione, la negazione o la creazione di un contesto di autorizzazione specifico del thread che è indipendente dal contesto di sicurezza a livello di applicazione possono dare luogo a un comportamento imprevisto. A seconda dell'applicazione, questo comportamento può comportare vulnerabilità di sicurezza a livello di applicazione.

Codice che chiama in WCF utilizzando un contesto di autorizzazione specifico del thread deve essere preparato a gestire le situazioni seguenti che possono verificarsi:

- Il contesto di sicurezza specifico del thread potrebbe non essere mantenuto per la durata dell'operazione, il che comporta potenziali eccezioni di sicurezza.

- Il codice WCF interno, nonché qualsiasi callback fornito dall'utente possono essere eseguite in un contesto di sicurezza diverso da quello in cui è iniziata originariamente la chiamata. Questi contesti includono:

  - Il contesto di autorizzazione dell'applicazione.

  - Qualsiasi contesto di autorizzazione specifico del thread creato in precedenza da altri thread utente usato per chiamare WCF nel corso della durata di esecuzione <xref:System.AppDomain>.

WCF garantisce che codice parzialmente attendibile non è possibile ottenere le autorizzazioni di attendibilità, a meno che tali autorizzazioni vengano asserite da un componente completamente attendibile prima della chiamata alle API pubbliche di WCF. Non garantisce, tuttavia, che gli effetti dell'asserzione di attendibilità totale siano isolati in un thread, operazione o azione dell'utente specifico.

Come procedura consigliata, evitare di creare un contesto di autorizzazione specifico del thread chiamando <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> o <xref:System.Security.PermissionSet.Deny%2A>. In alternativa, concedere o negare il privilegio all'applicazione stessa, così che non sia necessario <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> o <xref:System.Security.PermissionSet.PermitOnly%2A>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
