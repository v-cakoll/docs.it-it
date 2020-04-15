---
title: Serializzazione e metadati
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: cc9adf0e6627ef3190e74fea5d4f0f3afd581811
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389223"
---
# <a name="serialization-and-metadata"></a>Serializzazione e metadati

Se l'applicazione serializza e deserializza oggetti, potrebbe essere necessario aggiungere voci al file di direttive di runtime (rd.xml) per assicurarsi che i metadati necessari siano presenti in fase di esecuzione. Esistono due categorie di serializzatori e ciascuna richiede una gestione differente nel file di direttive di runtime:  
  
- Serializzatori di terze parti basati su reflection. Richiedono modifiche al file di direttive di runtime e sono descritti nella sezione successiva.  
  
- Serializzatori non basati su reflection trovati nella libreria di classi .NET Framework. Possono richiedere modifiche al file di direttive di runtime e sono descritti nella sezione [Serializzatori Microsoft](#Microsoft).  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a>Serializzatori di terze parti

 I serializzatori di terze parti, incluso Newtonsoft.JSON, sono in genere basati su reflection. Dato un oggetto binario di grandi dimensioni (BLOB) di dati serializzati, i campi dati vengono assegnati a un tipo concreto cercando i campi del tipo di destinazione per nome. Come minimo, l'uso di queste librerie causa eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) per ogni oggetto <xref:System.Type> che si prova a serializzare o deserializzare in una raccolta `List<Type>`.  
  
 Il modo più semplice per risolvere i problemi causati da metadati mancanti per questi serializzatori è raccogliere i tipi che verranno usati nella serializzazione in un singolo spazio dei nomi (ad esempio `App.Models`) e applicarvi una direttiva metadati `Serialize`:  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Per informazioni sulla sintassi utilizzata [ \<](namespace-element-net-native.md)nell'esempio, vedere Elemento> dello spazio dei nomi .  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a>Serializzatori Microsoft

 Nonostante le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Xml.Serialization.XmlSerializer> non si basino sulla reflection, richiedono che il codice venga generato in base all'oggetto da serializzare o deserializzare. I costruttori di overload per ciascun serializzatore includono un parametro <xref:System.Type> che specifica il tipo da serializzare o deserializzare. Il modo in cui si specifica che il tipo nel codice definisce l'azione che l'utente deve accettare, come illustrato nelle due sezioni.  
  
### <a name="typeof-used-in-the-constructor"></a>typeof usato nel costruttore

 Se si chiama un costruttore di queste classi di serializzazione e si include l'operatore [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) di C, **non è necessario eseguire alcuna operazione aggiuntiva.** Ad esempio, in ognuna delle seguenti chiamate a un costruttore di classe di serializzazione, la parola chiave `typeof` viene usata come parte dell'espressione passata al costruttore.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Il compilatore nativo di .NET gestirà automaticamente questo codice.  
  
### <a name="typeof-used-outside-the-constructor"></a>typeof usato fuori dal costruttore

 Se si chiama un costruttore di queste classi di serializzazione e si utilizza <xref:System.Type> l'operatore [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) di C' all'esterno dell'espressione fornita al parametro del costruttore, come nel codice seguente, il compilatore nativo di .NET non è in grado di risolvere il tipo:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 In questo caso, è necessario specificare il tipo nel file di direttive di runtime con l'aggiunta di una voce simile alla seguente:  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Analogamente, se si chiama <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> un costruttore, <xref:System.Type> ad esempio e si fornisce una matrice di oggetti aggiuntivi da serializzare, come nel codice seguente, il compilatore nativo di .NET non è in grado di risolvere questi tipi.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
Aggiungere voci come le seguenti per ogni tipo al file delle direttive di runtime:  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
Per informazioni sulla sintassi utilizzata [ \<](type-element-net-native.md)nell'esempio, vedere Elemento> Tipo .  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [\<Tipo> elemento](type-element-net-native.md)
- [\<Elemento> dello spazio dei nomiNamespace> Element](namespace-element-net-native.md)
