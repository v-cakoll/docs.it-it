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
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289655"
---
# <a name="custom-serialization"></a><span data-ttu-id="dd733-104">Serializzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="dd733-104">Custom serialization</span></span>
<span data-ttu-id="dd733-105">La serializzazione personalizzata è il processo di controllo della serializzazione e deserializzazione di un tipo.</span><span class="sxs-lookup"><span data-stu-id="dd733-105">Custom serialization is the process of controlling the serialization and deserialization of a type.</span></span> <span data-ttu-id="dd733-106">Tramite il controllo della serializzazione è possibile garantire la compatibilità della serializzazione stessa, ovvero la possibilità di eseguire la serializzazione e la deserializzazione tra versioni di un tipo senza compromettere la funzionalità principale del tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="dd733-106">By controlling serialization, it's possible to ensure serialization compatibility, which is the ability to serialize and deserialize between versions of a type without breaking the core functionality of the type.</span></span> <span data-ttu-id="dd733-107">Ad esempio, nella prima versione di un tipo potrebbero essere presenti solo due campi.</span><span class="sxs-lookup"><span data-stu-id="dd733-107">For example, in the first version of a type, there may be only two fields.</span></span> <span data-ttu-id="dd733-108">Nella versione successiva di un tipo, vengono aggiunti molti altri campi.</span><span class="sxs-lookup"><span data-stu-id="dd733-108">In the next version of a type, several more fields are added.</span></span> <span data-ttu-id="dd733-109">La seconda versione di un'applicazione deve comunque essere in grado di serializzare e deserializzare entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="dd733-109">Yet the second version of an application must be able to serialize and deserialize both types.</span></span> <span data-ttu-id="dd733-110">Nelle seguenti sezioni viene descritto come controllare la serializzazione:</span><span class="sxs-lookup"><span data-stu-id="dd733-110">The following sections describe how to control serialization.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> <span data-ttu-id="dd733-111">Nelle versioni precedenti a .NET Framework 4.0, la serializzazione di dati utente personalizzati in un assembly parzialmente attendibile era eseguita tramite GetObjectData.</span><span class="sxs-lookup"><span data-stu-id="dd733-111">In versions previous to .NET Framework 4.0, serialization of custom user data in a partially trusted assembly was accomplished using the GetObjectData.</span></span> <span data-ttu-id="dd733-112">A partire dalla versione 4.0 questo metodo è contrassegnato dall'attributo <xref:System.Security.SecurityCriticalAttribute> che impedisce esecuzione negli assembly parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="dd733-112">Starting with version 4.0, that method is marked with the <xref:System.Security.SecurityCriticalAttribute> attribute which prevents execution in partially trusted assemblies.</span></span> <span data-ttu-id="dd733-113">Per ovviare a questa condizione, implementare l'interfaccia <xref:System.Runtime.Serialization.ISafeSerializationData>.</span><span class="sxs-lookup"><span data-stu-id="dd733-113">To work around this condition, implement the <xref:System.Runtime.Serialization.ISafeSerializationData> interface.</span></span>  
  
## <a name="running-custom-methods-during-and-after-serialization"></a><span data-ttu-id="dd733-114">Esecuzione di metodi personalizzati durante e dopo la serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd733-114">Running custom methods during and after serialization</span></span>  
 <span data-ttu-id="dd733-115">La procedura consigliata e il modo più semplice (introdotto nella versione 2.0 di .NET Framework) consiste nell'applicare i seguenti attributi ai metodi utilizzati per correggere i dati durante e dopo la serializzazione:</span><span class="sxs-lookup"><span data-stu-id="dd733-115">The best practice and easiest way (introduced in version 2.0 of the .NET Framework) is to apply the following attributes to methods that are used to correct data during and after serialization:</span></span>  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 <span data-ttu-id="dd733-116">Tali attributi consentono al tipo di partecipare a una o a tutte le quattro fasi dei processi di serializzazione e deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-116">These attributes allow the type to participate in any one of, or all four of the phases, of the serialization and deserialization processes.</span></span> <span data-ttu-id="dd733-117">Gli attributi specificano i metodi del tipo che devono essere richiamati durante ogni fase.</span><span class="sxs-lookup"><span data-stu-id="dd733-117">The attributes specify the methods of the type that should be invoked during each phase.</span></span> <span data-ttu-id="dd733-118">I metodi non accedono al flusso di serializzazione ma consentono di modificare l'oggetto prima e dopo la serializzazione o prima e dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-118">The methods do not access the serialization stream but instead allow you to alter the object before and after serialization, or before and after deserialization.</span></span> <span data-ttu-id="dd733-119">Gli attributi possono essere applicati a tutti i livelli della gerarchia di ereditarietà del tipo e ogni metodo viene chiamato nella gerarchia dalla base al più derivato.</span><span class="sxs-lookup"><span data-stu-id="dd733-119">The attributes can be applied at all levels of the type inheritance hierarchy, and each method is called in the hierarchy from the base to the most derived.</span></span> <span data-ttu-id="dd733-120">Tale meccanismo consente di evitare la complessità e il rischio di problemi risultanti dall'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable>, dando la responsabilità della serializzazione e deserializzazione all'implementazione più derivata.</span><span class="sxs-lookup"><span data-stu-id="dd733-120">This mechanism avoids the complexity and any resulting issues of implementing the <xref:System.Runtime.Serialization.ISerializable> interface by giving the responsibility for serialization and deserialization to the most derived implementation.</span></span> <span data-ttu-id="dd733-121">Inoltre, tale meccanismo consente ai formattatori di ignorare l'inserimento di campi e il recupero dal flusso di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-121">Additionally, this mechanism allows the formatters to ignore the population of fields and retrieval from the serialization stream.</span></span> <span data-ttu-id="dd733-122">Per dettagli ed esempi di serializzazione e deserializzazione di controllo, fare clic su uno dei collegamenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="dd733-122">For details and examples of controlling serialization and deserialization, click any of the previous links.</span></span>  
  
 <span data-ttu-id="dd733-123">Inoltre, quando si aggiunge un nuovo campo a un tipo serializzabile esistente, applicare l'attributo <xref:System.Runtime.Serialization.OptionalFieldAttribute> al campo.</span><span class="sxs-lookup"><span data-stu-id="dd733-123">In addition, when adding a new field to an existing serializable type, apply the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to the field.</span></span> <span data-ttu-id="dd733-124">Le classi <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> e <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignorano l'assenza del campo se viene elaborato un flusso a cui risulta mancante il nuovo campo.</span><span class="sxs-lookup"><span data-stu-id="dd733-124">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignores the absence of the field when a stream that is missing the new field is processed.</span></span>  
  
## <a name="implementing-the-iserializable-interface"></a><span data-ttu-id="dd733-125">Implementazione dell'interfaccia ISerializable</span><span class="sxs-lookup"><span data-stu-id="dd733-125">Implementing the ISerializable interface</span></span>  
 <span data-ttu-id="dd733-126">L'altro modo per controllare la serializzazione prevede l'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable> per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dd733-126">The other way to control serialization is achieved by implementing the <xref:System.Runtime.Serialization.ISerializable> interface on an object.</span></span> <span data-ttu-id="dd733-127">Notare tuttavia che il metodo descritto nella sezione precedente sostituisce tale metodo per il controllo della serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-127">Note, however, that the method in the previous section supersedes this method to control serialization.</span></span>  
  
 <span data-ttu-id="dd733-128">In aggiunta, la serializzazione predefinita non deve essere usata per una classe contrassegnata con l'attributo [Serializable](xref:System.SerializableAttribute) e dotata di sicurezza dichiarativa o imperativa al livello della classe. La serializzazione non deve essere usata neanche per i costruttori di questa classe.</span><span class="sxs-lookup"><span data-stu-id="dd733-128">In addition, you should not use default serialization on a class that is marked with the [Serializable](xref:System.SerializableAttribute) attribute and has declarative or imperative security at the class level or on its constructors.</span></span> <span data-ttu-id="dd733-129">Tali classi devono invece implementare sempre l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="dd733-129">Instead, these classes should always implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 <span data-ttu-id="dd733-130">L'implementazione dell'interfaccia <xref:System.Runtime.Serialization.ISerializable> prevede l'implementazione del metodo `GetObjectData` e di un costruttore speciale usato quando l'oggetto viene deserializzato.</span><span class="sxs-lookup"><span data-stu-id="dd733-130">Implementing <xref:System.Runtime.Serialization.ISerializable> involves implementing the `GetObjectData` method and a special constructor that is used when the object is deserialized.</span></span> <span data-ttu-id="dd733-131">Nell'esempio di codice riportato di seguito viene mostrato come implementare l'interfaccia <xref:System.Runtime.Serialization.ISerializable> sulla classe `MyObject` da una sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="dd733-131">The following sample code shows how to implement <xref:System.Runtime.Serialization.ISerializable> on the `MyObject` class from a previous section.</span></span>  
  
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
  
 <span data-ttu-id="dd733-132">Se il metodo **GetObjectData** viene chiamato durante la serializzazione, è compito dell'utente popolare l'oggetto <xref:System.Runtime.Serialization.SerializationInfo> specificato con la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="dd733-132">When **GetObjectData** is called during serialization, you are responsible for populating the <xref:System.Runtime.Serialization.SerializationInfo> provided with the method call.</span></span> <span data-ttu-id="dd733-133">Aggiungere le variabili da serializzare come coppie di nomi e valori.</span><span class="sxs-lookup"><span data-stu-id="dd733-133">Add the variables to be serialized as name and value pairs.</span></span> <span data-ttu-id="dd733-134">Come nome è possibile utilizzare qualsiasi testo.</span><span class="sxs-lookup"><span data-stu-id="dd733-134">Any text can be used as the name.</span></span> <span data-ttu-id="dd733-135">È possibile decidere quali variabili membro vanno aggiunte a <xref:System.Runtime.Serialization.SerializationInfo>, purché vengano serializzati dati sufficienti per il ripristino dell'oggetto durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-135">You have the freedom to decide which member variables are added to the <xref:System.Runtime.Serialization.SerializationInfo>, provided that sufficient data is serialized to restore the object during deserialization.</span></span> <span data-ttu-id="dd733-136">Le classi derivate devono chiamare il metodo **GetObjectData** per l'oggetto di base se quest'ultimo implementa <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="dd733-136">Derived classes should call the **GetObjectData** method on the base object if the latter implements <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
 <span data-ttu-id="dd733-137">Notare che la serializzazione può consentire ad altro codice di visualizzare o modificare i dati dell'istanza dell'oggetto altrimenti inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="dd733-137">Note that serialization can allow other code to see or modify object instance data that is otherwise inaccessible.</span></span> <span data-ttu-id="dd733-138">Il codice che esegue la serializzazione, quindi, richiede [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato.</span><span class="sxs-lookup"><span data-stu-id="dd733-138">Therefore, code that performs serialization requires the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="dd733-139">In base ai criteri predefiniti, questa autorizzazione non è concessa a codice scaricato da Internet o a codice Intranet, ma solo al codice presente sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="dd733-139">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span> <span data-ttu-id="dd733-140">Il metodo **GetObjectData** deve essere protetto in modo esplicito tramite la richiesta di [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato o tramite la richiesta di altre autorizzazioni che consentono di proteggere i dati privati in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="dd733-140">The **GetObjectData** method must be explicitly protected either by demanding the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified or by demanding other permissions that specifically help protect private data.</span></span>  
  
 <span data-ttu-id="dd733-141">Se un campo privato memorizza informazioni riservate, è necessario proteggere i dati richiedendo le autorizzazioni appropriate per **GetObjectData**.</span><span class="sxs-lookup"><span data-stu-id="dd733-141">If a private field stores sensitive information, you should demand the appropriate permissions on **GetObjectData** to protect the data.</span></span> <span data-ttu-id="dd733-142">Si ricordi che il codice a cui è stato concesso [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag **SerializationFormatter** specificato può visualizzare e modificare i dati memorizzati nei campi privati.</span><span class="sxs-lookup"><span data-stu-id="dd733-142">Remember that code that has been granted [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the **SerializationFormatter** flag specified can view and modify the data stored in private fields.</span></span> <span data-ttu-id="dd733-143">Un chiamante dannoso a cui venga concesso l'attributo [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) può visualizzare dati quali percorsi di directory nascoste o autorizzazioni concesse e può usare tali dati per sfruttare una vulnerabilità di sicurezza nel computer.</span><span class="sxs-lookup"><span data-stu-id="dd733-143">A malicious caller granted this [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) can view data such as hidden directory locations or granted permissions and use the data to exploit a security vulnerability on the computer.</span></span> <span data-ttu-id="dd733-144">Per un elenco completo dei flag di autorizzazione di sicurezza che è possibile specificare, vedere l'[enumerazione SecurityPermissionFlag](xref:System.Security.Permissions.SecurityPermissionFlag).</span><span class="sxs-lookup"><span data-stu-id="dd733-144">For a complete list of the security permission flags you can specify, see the [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).</span></span>  
  
 <span data-ttu-id="dd733-145">È importante sottolineare che quando si aggiunge <xref:System.Runtime.Serialization.ISerializable> a una classe, è necessario implementare sia **GetObjectData** che il costruttore speciale.</span><span class="sxs-lookup"><span data-stu-id="dd733-145">It's important to stress that when <xref:System.Runtime.Serialization.ISerializable> is added to a class you must implement both **GetObjectData** and the special constructor.</span></span> <span data-ttu-id="dd733-146">Se **GetObjectData** manca, il compilatore visualizza un avviso.</span><span class="sxs-lookup"><span data-stu-id="dd733-146">The compiler warns you if **GetObjectData** is missing.</span></span> <span data-ttu-id="dd733-147">Tuttavia, poiché è impossibile applicare l'implementazione di un costruttore, non viene visualizzato alcun avviso nel caso in cui sia assente il costruttore e viene generata un'eccezione se si tenta di deserializzare una classe senza il costruttore.</span><span class="sxs-lookup"><span data-stu-id="dd733-147">However, because it is impossible to enforce the implementation of a constructor, no warning is provided if the constructor is absent, and an exception is thrown when an attempt is made to deserialize a class without the constructor.</span></span>  
  
 <span data-ttu-id="dd733-148">La progettazione corrente è stata preferita rispetto a un metodo <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> in modo da evitare eventuali problemi di sicurezza e di controllo della versione.</span><span class="sxs-lookup"><span data-stu-id="dd733-148">The current design was favored above a <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> method to get around potential security and versioning problems.</span></span> <span data-ttu-id="dd733-149">Ad esempio, un metodo `SetObjectData` deve essere pubblico se è definito come parte di un'interfaccia; in tal modo gli utenti devono scrivere codice per evitare che il metodo **SetObjectData** venga chiamato più volte.</span><span class="sxs-lookup"><span data-stu-id="dd733-149">For example, a `SetObjectData` method must be public if it is defined as part of an interface; thus users must write code to defend against having the **SetObjectData** method called multiple times.</span></span> <span data-ttu-id="dd733-150">In caso contrario, un'applicazione dannosa che chiami il metodo **SetObjectData** per un oggetto in fase di esecuzione di un'operazione può provocare problemi potenziali.</span><span class="sxs-lookup"><span data-stu-id="dd733-150">Otherwise, a malicious application that calls the **SetObjectData** method on an object in the process of executing an operation can cause potential problems.</span></span>  
  
 <span data-ttu-id="dd733-151">Durante la deserializzazione, <xref:System.Runtime.Serialization.SerializationInfo> viene passato alla classe tramite il costruttore fornito a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="dd733-151">During deserialization, <xref:System.Runtime.Serialization.SerializationInfo> is passed to the class using the constructor provided for this purpose.</span></span> <span data-ttu-id="dd733-152">Eventuali vincoli di visibilità posizionati sul costruttore vengono ignorati quando l'oggetto viene deserializzato; in tal modo è possibile contrassegnare la classe come pubblica, protetta, interna, o privata.</span><span class="sxs-lookup"><span data-stu-id="dd733-152">Any visibility constraints placed on the constructor are ignored when the object is deserialized; so you can mark the class as public, protected, internal, or private.</span></span> <span data-ttu-id="dd733-153">Tuttavia, è una procedura consigliata rendere il costruttore protetto a meno che la classe non sia sigillata; in tal caso il costruttore deve essere contrassegnato come privato.</span><span class="sxs-lookup"><span data-stu-id="dd733-153">However, it is a best practice to make the constructor protected unless the class is sealed, in which case the constructor should be marked private.</span></span> <span data-ttu-id="dd733-154">Il costruttore deve inoltre eseguire la convalida di input approfondita.</span><span class="sxs-lookup"><span data-stu-id="dd733-154">The constructor should also perform thorough input validation.</span></span> <span data-ttu-id="dd733-155">Per evitare un uso inappropriato da parte di codice dannoso, il costruttore deve applicare gli stessi controlli e autorizzazioni di sicurezza richiesti per ottenere un'istanza della classe mediante l'utilizzo di un qualunque altro costruttore.</span><span class="sxs-lookup"><span data-stu-id="dd733-155">To avoid misuse by malicious code, the constructor should enforce the same security checks and permissions required to obtain an instance of the class using any other constructor.</span></span> <span data-ttu-id="dd733-156">Se non si segue questo consiglio, il codice dannoso può preserializzare un oggetto, ottenere il controllo con [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) con il flag <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> specificato e deserializzare l'oggetto in un computer client, evitando qualsiasi misura di sicurezza applicata durante la costruzione standard dell'istanza tramite un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="dd733-156">If you do not follow this recommendation, malicious code can preserialize an object, obtain control with the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified and deserialize the object on a client computer bypassing any security that would have been applied during standard instance construction using a public constructor.</span></span>  
  
 <span data-ttu-id="dd733-157">Per ripristinare lo stato dell'oggetto, è sufficiente recuperare i valori delle variabili da <xref:System.Runtime.Serialization.SerializationInfo> utilizzando i nomi utilizzati durante la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-157">To restore the state of the object, simply retrieve the values of the variables from <xref:System.Runtime.Serialization.SerializationInfo> using the names used during serialization.</span></span> <span data-ttu-id="dd733-158">Se la classe di base implementa <xref:System.Runtime.Serialization.ISerializable>, il costruttore di base deve essere chiamato in modo da consentire all'oggetto di base di ripristinare le variabili.</span><span class="sxs-lookup"><span data-stu-id="dd733-158">If the base class implements <xref:System.Runtime.Serialization.ISerializable>, the base constructor should be called to allow the base object to restore its variables.</span></span>  
  
 <span data-ttu-id="dd733-159">Se si deriva una nuova classe da una classe che implementa <xref:System.Runtime.Serialization.ISerializable> e la classe derivata contiene variabili che devono essere serializzate, questa deve implementare sia il costruttore che il metodo **GetObjectData**.</span><span class="sxs-lookup"><span data-stu-id="dd733-159">When you derive a new class from one that implements <xref:System.Runtime.Serialization.ISerializable>, the derived class must implement both the constructor as well as the **GetObjectData** method if it has variables that need to be serialized.</span></span> <span data-ttu-id="dd733-160">Nell'esempio di codice riportato di seguito viene mostrato come viene eseguita tale operazione tramite l'utilizzo della classe `MyObject` mostrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dd733-160">The following code example shows how this is done using the `MyObject` class shown previously.</span></span>  
  
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
  
 <span data-ttu-id="dd733-161">Non dimenticare di chiamare la classe di base nel costruttore di deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-161">Don't forget to call the base class in the deserialization constructor.</span></span> <span data-ttu-id="dd733-162">Se tale operazione non viene eseguita, il costruttore per la classe di base non viene mai chiamato e l'oggetto non viene costruito completamente dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dd733-162">If this isn't done, the constructor on the base class is never called, and the object is not fully constructed after deserialization.</span></span>  
  
 <span data-ttu-id="dd733-163">Gli oggetti vengono ricostruiti dall'interno all'esterno; durante la deserializzazione, i metodi di chiamata possono avere effetti collaterali indesiderati, poiché i metodi chiamati potrebbero fare riferimento a riferimenti a oggetti che non sono stati deserializzati al momento dell'esecuzione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dd733-163">Objects are reconstructed from the inside out; and calling methods during deserialization can have undesirable side effects, because the methods called might refer to object references that have not been deserialized by the time the call is made.</span></span> <span data-ttu-id="dd733-164">Se la classe in fase di deserializzazione implementa <xref:System.Runtime.Serialization.IDeserializationCallback>, il metodo <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> viene chiamato automaticamente dopo la deserializzazione dell'intero oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="dd733-164">If the class being deserialized implements the <xref:System.Runtime.Serialization.IDeserializationCallback>, the <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> method is automatically called when the entire object graph has been deserialized.</span></span> <span data-ttu-id="dd733-165">In questa fase, tutti gli oggetti figlio a cui si fa riferimento sono stati ripristinati pienamente.</span><span class="sxs-lookup"><span data-stu-id="dd733-165">At this point, all the child objects referenced have been fully restored.</span></span> <span data-ttu-id="dd733-166">Una tabella hash è un esempio tipico di una classe difficile da deserializzare senza l'utilizzo del listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="dd733-166">A hash table is a typical example of a class that is difficult to deserialize without using the event listener.</span></span> <span data-ttu-id="dd733-167">È facile recuperare le coppie chiave/valore durante la deserializzazione, tuttavia aggiungere nuovamente tali oggetti alla tabella hash può provocare problemi, poiché non c'è nessuna garanzia che le classi derivate dalla tabella hash siano state deserializzate.</span><span class="sxs-lookup"><span data-stu-id="dd733-167">It is easy to retrieve the key and value pairs during deserialization, but adding these objects back to the hash table can cause problems, because there is no guarantee that classes that derived from the hash table have been deserialized.</span></span> <span data-ttu-id="dd733-168">I metodi di chiamata su una tabella hash in questa fase non sono pertanto consigliabili.</span><span class="sxs-lookup"><span data-stu-id="dd733-168">Calling methods on a hash table at this stage is therefore not advisable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd733-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd733-169">See also</span></span>

- [<span data-ttu-id="dd733-170">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="dd733-170">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="dd733-171">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="dd733-171">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="dd733-172">Sicurezza e serializzazione</span><span class="sxs-lookup"><span data-stu-id="dd733-172">Security and Serialization</span></span>](../../framework/misc/security-and-serialization.md)
