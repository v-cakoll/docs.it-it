---
title: Serializzazione personalizzata
description: La serializzazione personalizzata sta controllando la serializzazione e la deserializzazione di un tipo. Controllare la serializzazione può garantire la compatibilità della serializzazione.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binary serialization, custom serialization
- custom serialization
- binary serialization, controlling
- OptionalFieldAttribute class, custom serialization
- ISerializable interface, custom serialization
- OnDeserializingAttribute class, custom serialization
- OnSerializedAttribute class, custom serialization
- serialization, custom serialization
- serialization, controlling
- OnDeserializedAttribute class, custom serialization
- OnSerializingAttribute class, custom serialization
ms.assetid: 12ed422d-5280-49b8-9b71-a2ed129c0384
ms.openlocfilehash: 1532c4eeb09e7110d0f369ec47f342256889e576
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289655"
---
# <a name="custom-serialization"></a>Serializzazione personalizzata
La serializzazione personalizzata è il processo di controllo della serializzazione e deserializzazione di un tipo. Tramite il controllo della serializzazione è possibile garantire la compatibilità della serializzazione stessa, ovvero la possibilità di eseguire la serializzazione e la deserializzazione tra versioni di un tipo senza compromettere la funzionalità principale del tipo stesso. Ad esempio, nella prima versione di un tipo potrebbero essere presenti solo due campi. Nella versione successiva di un tipo, vengono aggiunti molti altri campi. La seconda versione di un'applicazione deve comunque essere in grado di serializzare e deserializzare entrambi i tipi. Nelle seguenti sezioni viene descritto come controllare la serializzazione:

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> Nelle versioni precedenti a .NET Framework 4.0, la serializzazione di dati utente personalizzati in un assembly parzialmente attendibile era eseguita tramite GetObjectData. A partire dalla versione 4.0 questo metodo è contrassegnato dall'attributo <xref:System.Security.SecurityCriticalAttribute> che impedisce esecuzione negli assembly parzialmente attendibili. Per ovviare a questa condizione, implementare l'interfaccia <xref:System.Runtime.Serialization.ISafeSerializationData>.  
  
## <a name="running-custom-methods-during-and-after-serialization"></a>Esecuzione di metodi personalizzati durante e dopo la serializzazione  
 La procedura consigliata e il modo più semplice (introdotto nella versione 2.0 di .NET Framework) consiste nell'applicare i seguenti attributi ai metodi utilizzati per correggere i dati durante e dopo la serializzazione:  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 Tali attributi consentono al tipo di partecipare a una o a tutte le quattro fasi dei processi di serializzazione e deserializzazione. Gli attributi specificano i metodi del tipo che devono essere richiamati durante ogni fase. I metodi non accedono al flusso di serializzazione ma consentono di modificare l'oggetto prima e dopo la serializzazione o prima e dopo la deserializzazione. Gli attributi possono essere applicati a tutti i livelli della gerarchia di ereditarietà del tipo e ogni metodo viene chiamato nella gerarchia dalla base al più derivato. Tale meccanismo consente di evitare la complessità e il rischio di problemi risultanti dall'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable>, dando la responsabilità della serializzazione e deserializzazione all'implementazione più derivata. Inoltre, tale meccanismo consente ai formattatori di ignorare l'inserimento di campi e il recupero dal flusso di serializzazione. Per dettagli ed esempi di serializzazione e deserializzazione di controllo, fare clic su uno dei collegamenti precedenti.  
  
 Inoltre, quando si aggiunge un nuovo campo a un tipo serializzabile esistente, applicare l'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> al campo. Le classi <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> e <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignorano l'assenza del campo se viene elaborato un flusso a cui risulta mancante il nuovo campo.  
  
## <a name="implementing-the-iserializable-interface"></a>Implementazione dell'interfaccia ISerializable  
 L'altro modo per controllare la serializzazione prevede l'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable> per un oggetto. Notare tuttavia che il metodo descritto nella sezione precedente sostituisce tale metodo per il controllo della serializzazione.  
  
 In aggiunta, la serializzazione predefinita non deve essere usata per una classe contrassegnata con l'attributo [Serializable](xref:System.SerializableAttribute) e dotata di sicurezza dichiarativa o imperativa al livello della classe. La serializzazione non deve essere usata neanche per i costruttori di questa classe. Tali classi devono invece implementare sempre l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.  
  
 L'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable> prevede l'implementazione del metodo `GetObjectData` e di un costruttore speciale usato quando l'oggetto viene deserializzato. Nell'esempio di codice riportato di seguito viene mostrato come implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable> sulla classe `MyObject` da una sezione precedente.  
  
```csharp
[Serializable]
public class MyObject : ISerializable
{
    public int n1;
    public int n2;
    public String str;

    public MyObject()
    {
    }

    protected MyObject(SerializationInfo info, StreamingContext context)
    {
      n1 = info.GetInt32("i");
      n2 = info.GetInt32("j");
      str = info.GetString("k");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public virtual void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        info.AddValue("i", n1);
        info.AddValue("j", n2);
        info.AddValue("k", str);
    }
}
```

```vb
<Serializable()>  _
Public Class MyObject
    Implements ISerializable
    Public n1 As Integer
    Public n2 As Integer
    Public str As String

    Public Sub New()
    End Sub

    Protected Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        n1 = info.GetInt32("i")
        n2 = info.GetInt32("j")
        str = info.GetString("k")
    End Sub 'New

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overridable Sub GetObjectData(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        info.AddValue("i", n1)
        info.AddValue("j", n2)
        info.AddValue("k", str)
    End Sub
End Class
```  
  
 Se il metodo **GetObjectData** viene chiamato durante la serializzazione, è compito dell'utente popolare l'oggetto <xref:System.Runtime.Serialization.SerializationInfo> specificato con la chiamata al metodo. Aggiungere le variabili da serializzare come coppie di nomi e valori. Come nome è possibile utilizzare qualsiasi testo. È possibile decidere quali variabili membro vanno aggiunte a <xref:System.Runtime.Serialization.SerializationInfo>, purché vengano serializzati dati sufficienti per il ripristino dell'oggetto durante la deserializzazione. Le classi derivate devono chiamare il metodo **GetObjectData** per l'oggetto di base se quest'ultimo implementa <xref:System.Runtime.Serialization.ISerializable>.  
  
 Notare che la serializzazione può consentire ad altro codice di visualizzare o modificare i dati dell'istanza dell'oggetto altrimenti inaccessibili. Il codice che esegue la serializzazione, quindi, richiede [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato. In base ai criteri predefiniti, questa autorizzazione non è concessa a codice scaricato da Internet o a codice Intranet, ma solo al codice presente sul computer locale. Il metodo **GetObjectData** deve essere protetto in modo esplicito tramite la richiesta di [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato o tramite la richiesta di altre autorizzazioni che consentono di proteggere i dati privati in modo specifico.  
  
 Se un campo privato memorizza informazioni riservate, è necessario proteggere i dati richiedendo le autorizzazioni appropriate per **GetObjectData**. Si ricordi che il codice a cui è stato concesso [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag **SerializationFormatter** specificato può visualizzare e modificare i dati memorizzati nei campi privati. Un chiamante dannoso a cui venga concesso l'attributo [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) può visualizzare dati quali percorsi di directory nascoste o autorizzazioni concesse e può usare tali dati per sfruttare una vulnerabilità di sicurezza nel computer. Per un elenco completo dei flag di autorizzazione di sicurezza che è possibile specificare, vedere l'[enumerazione SecurityPermissionFlag](xref:System.Security.Permissions.SecurityPermissionFlag).  
  
 È importante sottolineare che quando si aggiunge <xref:System.Runtime.Serialization.ISerializable> a una classe, è necessario implementare sia **GetObjectData** che il costruttore speciale. Se **GetObjectData** manca, il compilatore visualizza un avviso. Tuttavia, poiché è impossibile applicare l'implementazione di un costruttore, non viene visualizzato alcun avviso nel caso in cui sia assente il costruttore e viene generata un'eccezione se si tenta di deserializzare una classe senza il costruttore.  
  
 La progettazione corrente è stata preferita rispetto a un metodo <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> in modo da evitare eventuali problemi di sicurezza e di controllo della versione. Ad esempio, un metodo `SetObjectData` deve essere pubblico se è definito come parte di un'interfaccia; in tal modo gli utenti devono scrivere codice per evitare che il metodo **SetObjectData** venga chiamato più volte. In caso contrario, un'applicazione dannosa che chiami il metodo **SetObjectData** per un oggetto in fase di esecuzione di un'operazione può provocare problemi potenziali.  
  
 Durante la deserializzazione, <xref:System.Runtime.Serialization.SerializationInfo> viene passato alla classe tramite il costruttore fornito a tale scopo. Eventuali vincoli di visibilità posizionati sul costruttore vengono ignorati quando l'oggetto viene deserializzato; in tal modo è possibile contrassegnare la classe come pubblica, protetta, interna, o privata. Tuttavia, è una procedura consigliata rendere il costruttore protetto a meno che la classe non sia sigillata; in tal caso il costruttore deve essere contrassegnato come privato. Il costruttore deve inoltre eseguire la convalida di input approfondita. Per evitare un uso inappropriato da parte di codice dannoso, il costruttore deve applicare gli stessi controlli e autorizzazioni di sicurezza richiesti per ottenere un'istanza della classe mediante l'utilizzo di un qualunque altro costruttore. Se non si segue questo consiglio, il codice dannoso può preserializzare un oggetto, ottenere il controllo con [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato e deserializzare l'oggetto in un computer client, evitando qualsiasi misura di sicurezza applicata durante la costruzione standard dell'istanza tramite un costruttore pubblico.  
  
 Per ripristinare lo stato dell'oggetto, è sufficiente recuperare i valori delle variabili da <xref:System.Runtime.Serialization.SerializationInfo> utilizzando i nomi utilizzati durante la serializzazione. Se la classe di base implementa <xref:System.Runtime.Serialization.ISerializable>, il costruttore di base deve essere chiamato in modo da consentire all'oggetto di base di ripristinare le variabili.  
  
 Se si deriva una nuova classe da una classe che implementa <xref:System.Runtime.Serialization.ISerializable> e la classe derivata contiene variabili che devono essere serializzate, questa deve implementare sia il costruttore che il metodo **GetObjectData**. Nell'esempio di codice riportato di seguito viene mostrato come viene eseguita tale operazione tramite l'utilizzo della classe `MyObject` mostrata in precedenza.  
  
```csharp
[Serializable]
public class ObjectTwo : MyObject
{
    public int num;

    public ObjectTwo()
      : base()
    {
    }

    protected ObjectTwo(SerializationInfo si, StreamingContext context)
      : base(si, context)
    {
        num = si.GetInt32("num");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public override void GetObjectData(SerializationInfo si, StreamingContext context)
    {
        base.GetObjectData(si,context);
        si.AddValue("num", num);
    }
}
```

```vb
<Serializable()>  _
Public Class ObjectTwo
    Inherits MyObject
    Public num As Integer

    Public Sub New()

    End Sub

    Protected Sub New(ByVal si As SerializationInfo, _
    ByVal context As StreamingContext)
        MyBase.New(si, context)
        num = si.GetInt32("num")
    End Sub

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overrides Sub GetObjectData(ByVal si As SerializationInfo, ByVal context As StreamingContext)
        MyBase.GetObjectData(si, context)
        si.AddValue("num", num)
    End Sub
End Class
```  
  
 Non dimenticare di chiamare la classe di base nel costruttore di deserializzazione. Se tale operazione non viene eseguita, il costruttore per la classe di base non viene mai chiamato e l'oggetto non viene costruito completamente dopo la deserializzazione.  
  
 Gli oggetti vengono ricostruiti dall'interno all'esterno; durante la deserializzazione, i metodi di chiamata possono avere effetti collaterali indesiderati, poiché i metodi chiamati potrebbero fare riferimento a riferimenti a oggetti che non sono stati deserializzati al momento dell'esecuzione della chiamata. Se la classe in fase di deserializzazione implementa <xref:System.Runtime.Serialization.IDeserializationCallback>, il metodo <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> viene chiamato automaticamente dopo la deserializzazione dell'intero oggetto grafico. In questa fase, tutti gli oggetti figlio a cui si fa riferimento sono stati ripristinati pienamente. Una tabella hash è un esempio tipico di una classe difficile da deserializzare senza l'utilizzo del listener di eventi. È facile recuperare le coppie chiave/valore durante la deserializzazione, tuttavia aggiungere nuovamente tali oggetti alla tabella hash può provocare problemi, poiché non c'è nessuna garanzia che le classi derivate dalla tabella hash siano state deserializzate. I metodi di chiamata su una tabella hash in questa fase non sono pertanto consigliabili.  
  
## <a name="see-also"></a>Vedi anche

- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- [Sicurezza e serializzazione](../../framework/misc/security-and-serialization.md)
