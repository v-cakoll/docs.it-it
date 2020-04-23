---
title: 'Procedura dettagliata: creazione di codice in scenari di attendibilità parziale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- reflection emit, anonymously hosted dynamic methods
- partial trust, reflection
- partial trust, emitting dynamic methods
- reflection emit, partial trust scenarios
- anonymously hosted dynamic methods [.NET Framework]
- emitting dynamic assemblies,partial trust scenarios
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
ms.openlocfilehash: fd420c9754494b95c55df403edec87743572db03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129984"
---
# <a name="walkthrough-emitting-code-in-partial-trust-scenarios"></a>Procedura dettagliata: creazione di codice in scenari di attendibilità parziale

La reflection emit usa le stesse API in scenari di attendibilità sia parziale che completa, ma alcune funzionalità richiedono autorizzazioni speciali nel codice parzialmente attendibile. Inoltre, la reflection emit include una funzionalità, i metodi dinamici ospitati in modo anonimo, progettata per l'uso in situazioni di attendibilità parziale da parte di assembly trasparenti per la sicurezza.

> [!NOTE]
> Prima di .NET Framework 3.5, la creazione di codice richiedeva <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit?displayProperty=nameWithType>. Questa autorizzazione è inclusa per impostazione predefinita nei set di autorizzazioni denominati `FullTrust` e `Intranet`, ma non nel set di autorizzazioni `Internet`. Di conseguenza, una libreria può essere usata con attendibilità parziale solo se in essa era presente l'attributo <xref:System.Security.SecurityCriticalAttribute> e veniva eseguito un metodo <xref:System.Security.PermissionSet.Assert%2A> per <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>. Tali librerie richiedono un'attenta revisione della sicurezza perché eventuali errori nel codice potrebbe produrre delle vulnerabilità. .NET Framework 3.5 consente di generare codice in scenari con attendibilità parziale senza creare alcuna richiesta di sicurezza, poiché la generazione di codice non è implicitamente un'operazione con privilegi. Ovvero, il codice generato non dispone di ulteriori autorizzazioni rispetto all'assembly che lo genera. Questo consente alle librerie che generano il codice di essere trasparenti per la sicurezza ed elimina la necessità di asserire <xref:System.Security.Permissions.ReflectionPermissionFlag.ReflectionEmit>, quindi la scrittura di una libreria protetta non richiede una revisione completa della sicurezza.

Vengono illustrate le attività seguenti:

- [Configurazione di un oggetto sandbox semplice per il test del codice parzialmente attendibile](#Setting_up).

  > [!IMPORTANT]
  > Questo è un modo semplice per sperimentare il codice in situazioni di attendibilità parziale. Per eseguire codice realmente proveniente da percorsi non attendibili, vedere la [procedura relativa all'esecuzione di codice parzialmente attendibile in un oggetto sandbox](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

- [Esecuzione di codice in domini di applicazioni parzialmente attendibili](#Running_code).

- [Uso di metodi dinamici ospitati in modo anonimo per generare ed eseguire codice in situazioni di attendibilità parziale](#Using_methods).

Per altre informazioni sulla generazione di codice in scenari di attendibilità parziale, vedere la sezione relativa ai [problemi di sicurezza nella reflection emit](security-issues-in-reflection-emit.md).

Per un elenco completo del codice riportato in queste procedure, vedere la [sezione degli esempi](#Example) alla fine di questa procedura dettagliata.

<a name="Setting_up"></a>

## <a name="setting-up-partially-trusted-locations"></a>Impostazione di percorsi parzialmente attendibili

Le due procedure seguenti illustrano come impostare i percorsi da cui è possibile testare il codice con attendibilità parziale.

- La prima procedura spiega come creare un dominio dell'applicazione sandbox in cui vengono concesse autorizzazioni Internet al codice.

- La seconda procedura illustra come aggiungere <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> a un dominio dell'applicazione parzialmente attendibile, per consentire l'accesso ai dati privati negli assembly con attendibilità uguale o inferiore.

### <a name="creating-sandboxed-application-domains"></a>Creazione di domini dell'applicazione sandbox

Per creare un dominio applicazione in cui gli assembly sono eseguiti con attendibilità parziale, è necessario specificare il set di autorizzazioni da concedere agli assembly usando l'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> per creare il dominio dell'applicazione. Il modo più semplice per specificare il set di concessioni è recuperare un set di autorizzazioni denominato dai criteri di sicurezza.

Nella procedura seguente viene creato un dominio dell'applicazione sandbox che esegue il codice con attendibilità parziale, per testare gli scenari in cui il codice generato può accedere solo ai membri pubblici dei tipi pubblici. Una procedura successiva illustra come aggiungere <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess>, per testare scenari in cui il codice generato può accedere a tipi e membri non pubblici negli assembly a cui vengono concesse autorizzazioni uguali o inferiori.

#### <a name="to-create-an-application-domain-with-partial-trust"></a>Per creare un dominio dell'applicazione con attendibilità parziale

1. Creare un set di autorizzazioni da concedere agli assembly nel dominio dell'applicazione sandbox. In questo caso viene usato il set di autorizzazioni dell'area Internet.

    [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
    [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]

2. Creare un oggetto <xref:System.AppDomainSetup> per inizializzare il dominio dell'applicazione con un percorso dell'applicazione.

    > [!IMPORTANT]
    > Per semplicità, questo esempio di codice usa la cartella corrente. Per eseguire codice realmente proveniente da Internet, usare una cartella separata per il codice non attendibile, come descritto nella [procedura relativa all'esecuzione di codice parzialmente attendibile in un oggetto sandbox](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).

    [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
    [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]

3. Creare il dominio dell'applicazione, specificando le informazioni di configurazione del dominio dell'applicazione e il set di concessioni per tutti gli assembly eseguiti nel dominio dell'applicazione.

    [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
    [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]

    L'ultimo parametro dell'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> consente di specificare un set di assembly a cui deve essere concessa l'attendibilità totale, anziché il set di concessioni del dominio dell'applicazione. Non è necessario specificare gli assembly .NET Framework usati dall'applicazione, perché si trovano nella Global Assembly Cache. Gli assembly nella Global Assembly Cache sono sempre completamente attendibili. È possibile usare questo parametro per specificare assembly con nome sicuro che non sono presenti nella Global Assembly Cache.

### <a name="adding-restrictedmemberaccess-to-sandboxed-domains"></a>Aggiunta di RestrictedMemberAccess ai domini sandbox

Le applicazioni host possono consentire ai metodi dinamici ospitati in modo anonimo di accedere ai dati privati negli assembly con livelli di attendibilità uguali o inferiori a quelli dell'assembly che genera il codice. Per abilitare la possibilità limitata di ignorare i controlli di visibilità just-in-time (JIT), l'applicazione host aggiunge un oggetto <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> (RMA) al set di concessioni.

Ad esempio, un host può concedere alle applicazioni Internet autorizzazioni Internet più RMA, in modo tale che un'applicazione Internet sia in grado di generare codice che accede ai dati privati nei propri assembly. Poiché l'accesso è limitato agli assembly con attendibilità uguale o minore, un'applicazione Internet non può accedere a membri di assembly completamente attendibili, ad esempio gli assembly .NET Framework.

> [!NOTE]
> Per evitare l'elevazione dei privilegi, le informazioni sullo stack per l'assembly di creazione vengono incluse quando si creano metodi dinamici ospitati in modo anonimo. Quando il metodo viene richiamato, vengono controllate le informazioni sullo stack. Di conseguenza, un metodo dinamico ospitato in modo anonimo richiamato da codice completamente attendibile è comunque limitato al livello di attendibilità dell'assembly di creazione.

#### <a name="to-create-an-application-domain-with-partial-trust-plus-rma"></a>Per creare un dominio dell'applicazione con attendibilità parziale più RMA

1. Creare un nuovo oggetto <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> (RMA) e usare il metodo <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=nameWithType> per aggiungere l'autorizzazione al set di concessioni.

    [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
    [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]

    Il metodo <xref:System.Security.PermissionSet.AddPermission%2A> aggiunge l'autorizzazione al set di concessioni, se non è già inclusa. Se l'autorizzazione è già inclusa nel set di concessioni, i flag specificati vengono aggiunti all'autorizzazione esistente.

    > [!NOTE]
    > RMA è una funzionalità dei metodi dinamici ospitati in modo anonimo. Quando i metodi dinamici comuni ignorano i controlli di visibilità JIT, il codice generato richiede l'attendibilità totale.

2. Creare il dominio dell'applicazione, specificando le informazioni di configurazione del dominio dell'applicazione e il set di concessioni.

    [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
    [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]

<a name="Running_code"></a>

## <a name="running-code-in-sandboxed-application-domains"></a>Esecuzione di codice nei domini dell'applicazione sandbox

La procedura seguente spiega come definire una classe usando metodi che possono essere eseguiti in un dominio dell'applicazione, come creare un'istanza della classe nel dominio e come eseguire i relativi metodi.

#### <a name="to-define-and-execute-a-method-in-an-application-domain"></a>Per definire ed eseguire un metodo in un dominio dell'applicazione

1. Definire una classe che deriva da <xref:System.MarshalByRefObject>. Ciò consente di creare istanze della classe in altri domini dell'applicazione e di effettuare chiamate al metodo tra i limiti del dominio dell'applicazione. La classe di questo esempio è denominata `Worker`.

    [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
    [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]

2. Definire un metodo pubblico che contenga il codice da eseguire. In questo esempio, il codice genera un metodo dinamico semplice, crea un delegato per eseguire il metodo e richiama il delegato.

    [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
    [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]

3. Nel programma principale ottenere il nome visualizzato dell'assembly. Questo nome viene usato quando si creano istanze della classe `Worker` nel dominio dell'applicazione sandbox.

    [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
    [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]

4. Nel programma principale creare un dominio dell'applicazione sandbox, come descritto nella [prima procedura](#Setting_up) in questa procedura dettagliata. Non è necessario aggiungere autorizzazioni al set di autorizzazioni `Internet`, poiché il metodo `SimpleEmitDemo` usa solo metodi pubblici.

5. Nel programma principale creare un'istanza della classe `Worker` nel dominio dell'applicazione sandbox.

    [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
    [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]

    Il metodo <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> crea l'oggetto nel dominio dell'applicazione di destinazione e restituisce un proxy che può essere usato per chiamare le proprietà e metodi dell'oggetto.

    > [!NOTE]
    > Se questo codice viene utilizzato in Visual Studio, è necessario modificare il nome della classe per includere lo spazio dei nomi. Per impostazione predefinita, lo spazio dei nomi è il nome del progetto. Ad esempio, se il progetto è "PartialTrust", il nome della classe deve essere "PartialTrust.Worker".

6. Aggiungere il codice per chiamare il metodo `SimpleEmitDemo` . La chiamata viene sottoposta a marshalling entro i limiti del dominio dell'applicazione e il codice viene eseguito nel dominio dell'applicazione sandbox.

    [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
    [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]

<a name="Using_methods"></a>

## <a name="using-anonymously-hosted-dynamic-methods"></a>Uso dei metodi dinamici ospitati in modo anonimo

I metodi dinamici ospitati in modo anonimo sono associati a un assembly trasparente messo a disposizione dal sistema. Di conseguenza, il codice che contengono è trasparente. I metodi dinamici comuni, d'altra parte, devono essere associati a un modulo esistente, specificato direttamente o derivato da un tipo associato, e ricevono il livello di sicurezza da tale modulo.

> [!NOTE]
> L'unico modo di associare un metodo dinamico all'assembly che offre l'hosting anonimo è usare i costruttori descritti nella procedura seguente. Non è possibile specificare in modo esplicito un modulo nell'assembly di hosting anonimo.

I metodi dinamici comuni hanno accesso ai membri interni del modulo a cui sono associati o ai membri privati del tipo a cui sono associati. Poiché i metodi dinamici ospitati in modo anonimo sono isolati dall'altro codice, non hanno accesso ai dati privati. Usano tuttavia una possibilità limitata per ignorare i controlli di visibilità JIT in modo da ottenere l'accesso ai dati privati. Tale possibilità è limitata agli assembly con livelli di attendibilità uguali o inferiori a quello dell'assembly che genera il codice.

Per evitare l'elevazione dei privilegi, le informazioni sullo stack per l'assembly di creazione vengono incluse quando si creano metodi dinamici ospitati in modo anonimo. Quando il metodo viene richiamato, vengono controllate le informazioni sullo stack. Un metodo dinamico ospitato in modo anonimo richiamato da un codice completamente attendibile è comunque limitato al livello di attendibilità dell'assembly in cui è stato creato.

#### <a name="to-use-anonymously-hosted-dynamic-methods"></a>Per usare i metodi dinamici ospitati in modo anonimo

- Creare un metodo dinamico ospitato in modo anonimo usando un costruttore che non specifica un modulo o un tipo associato.

  [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
  [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]

  Se un metodo dinamico ospitato in modo anonimo usa solo tipi e metodi pubblici, non richiede l'accesso limitato al membro e non è necessario ignorare i controlli di visibilità JIT.

  Non sono richieste autorizzazioni speciali per generare un metodo dinamico, ma per il codice generato sono necessarie le autorizzazioni obbligatorie per i tipi e i metodi usati. Ad esempio, se il codice generato chiama un metodo che accede a un file, richiede <xref:System.Security.Permissions.FileIOPermission>. Se il livello di attendibilità non include tale autorizzazione, viene generata un'eccezione di sicurezza quando viene eseguito il codice generato. Il codice riportato di seguito genera un metodo dinamico che usa solo il metodo <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>. Di conseguenza, il codice può essere eseguito da percorsi parzialmente attendibili.

- In alternativa, creare un metodo dinamico ospitato in modo anonimo con la possibilità limitata di ignorare i controlli di visibilità JIT, usando il costruttore <xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> e specificando `true` per il parametro `restrictedSkipVisibility`.

  [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
  [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]

  La limitazione consiste nel fatto che il metodo dinamico ospitato in modo anonimo può accedere ai dati privati solo negli assembly con livelli di attendibilità uguali o inferiori a quello dell'assembly di creazione. Ad esempio, se il metodo dinamico è in esecuzione con attendibilità Internet, può accedere ai dati privati in altri assembly in esecuzione con attendibilità Internet, ma non può accedere ai dati privati degli assembly .NET Framework. Gli assembly .NET Framework sono installati nella Global Assembly Cache e sono sempre completamente attendibili.

  I metodi dinamici ospitati in modo anonimo possono usare questa possibilità limitata di ignorare i controlli di visibilità JIT solo se l'applicazione host concede <xref:System.Security.Permissions.ReflectionPermission> con il flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType>. La richiesta di questa autorizzazione viene effettuata quando viene richiamato il metodo.

  > [!NOTE]
  > Le informazioni sullo stack di chiamate per l'assembly di creazione vengono incluse quando viene costruito il metodo dinamico. Di conseguenza, la richiesta viene effettuata facendo riferimento alle autorizzazioni dell'assembly di creazione anziché a quelle dell'assembly che richiama il metodo. Ciò impedisce che il codice generato venga eseguito con autorizzazioni elevate.

  L'[esempio di codice completo](#Example) alla fine di questa procedura dettagliata illustra l'uso e le limitazioni dell'accesso limitato al membro. La relativa classe `Worker` include un metodo in grado di creare metodi dinamici ospitati in modo anonimo con o senza la possibilità limitata di ignorare i controlli di visibilità e l'esempio illustra il risultato dell'esecuzione di questo metodo nei domini dell'applicazione con diversi livelli di attendibilità.

  > [!NOTE]
  > La possibilità limitata di ignorare i controlli di visibilità è una funzionalità di metodi dinamici ospitati in modo anonimo. Quando i metodi dinamici comuni ignorano i controlli di visibilità JIT, deve essere concessa l'attendibilità totale.

<a name="Example"></a>

## <a name="example"></a>Esempio

### <a name="description"></a>Descrizione

Nell'esempio di codice riportato di seguito viene illustrato l'uso del flag <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess> per consentire ai metodi dinamici ospitati in modo anonimo di ignorare i controlli di visibilità JIT, ma solo quando il membro di destinazione è un livello uguale o inferiore di attendibilità rispetto all'assembly che genera il codice.

Nell'esempio viene definita una classe `Worker` che può essere sottoposta a marshalling entro i limiti del dominio dell'applicazione. La classe ha due overload del metodo `AccessPrivateMethod` che generano ed eseguono i metodi dinamici. Il primo overload genera un metodo dinamico che chiama il metodo privato `PrivateMethod` della classe `Worker` e può generare il metodo dinamico con o senza controlli di visibilità JIT. Il secondo overload genera un metodo dinamico che accede a una proprietà `internal` (proprietà `Friend` in Visual Basic) della classe <xref:System.String>.

L'esempio usa un metodo helper per creare un set di concessioni limitato alle autorizzazioni `Internet`, quindi crea un dominio dell'applicazione usando l'overload del metodo <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> per specificare che tutto il codice eseguito nel dominio usa questo set di concessioni. Nell'esempio viene creata un'istanza della classe `Worker` nel dominio dell'applicazione e viene eseguito due volte il metodo `AccessPrivateMethod`.

- La prima volta che il metodo `AccessPrivateMethod` viene eseguito, vengono applicati i controlli di visibilità JIT. Il metodo dinamico ha esito negativo quando viene richiamato, perché i controlli di visibilità JIT impediscono l'accesso al metodo privato.

- La seconda volta che il metodo `AccessPrivateMethod` viene eseguito, i controlli di visibilità JIT vengono ignorati. Il metodo dinamico ha esito negativo quando viene compilato, poiché il set di concessioni `Internet` non concede autorizzazioni sufficienti per ignorare i controlli di visibilità.

Nell'esempio viene aggiunto <xref:System.Security.Permissions.ReflectionPermission> con <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> al set di concessioni. Viene quindi creato un secondo dominio, specificando che a tutto il codice eseguito nel dominio vengano concesse le autorizzazioni del nuovo set di concessioni. Viene creata un'istanza della classe `Worker` nel nuovo dominio dell'applicazione e vengono eseguiti entrambi gli overload del metodo `AccessPrivateMethod`.

- Viene eseguito il primo overload del metodo `AccessPrivateMethod` e i controlli di visibilità JIT vengono ignorati. Il metodo dinamico viene compilato ed eseguito correttamente, poiché l'assembly che genera il codice è lo stesso assembly che contiene il metodo privato. Di conseguenza, i livelli di attendibilità sono uguali. Se l'applicazione che contiene la classe `Worker` ha diversi assembly, l'esito del processo sarà lo stesso per tutti gli assembly, poiché sono tutti allo stesso livello di attendibilità.

- Viene eseguito il secondo overload del metodo `AccessPrivateMethod` e i controlli di visibilità JIT vengono di nuovo ignorati. Questa volta il metodo dinamico ha esito negativo quando viene compilato, perché tenta di accedere `internal` `FirstChar` alla proprietà della <xref:System.String> classe. L'assembly che contiene la classe <xref:System.String> è completamente attendibile. Si trova quindi a un livello di attendibilità superiore rispetto all'assembly che genera il codice.

Questo confronto spiega come <xref:System.Security.Permissions.ReflectionPermissionFlag.RestrictedMemberAccess?displayProperty=nameWithType> consente al codice parzialmente attendibile di ignorare i controlli di visibilità per altro codice parzialmente attendibile senza compromettere la sicurezza del codice attendibile.

### <a name="code"></a>Codice

[!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
[!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]

## <a name="compiling-the-code"></a>Compilazione del codice

- Se si compila questo esempio di codice in Visual Studio, è necessario modificare il nome della classe in modo che includa lo spazio dei nomi quando si passa la classe al metodo <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>. Per impostazione predefinita, lo spazio dei nomi è il nome del progetto. Ad esempio, se il progetto è "PartialTrust", il nome della classe deve essere "PartialTrust.Worker".

## <a name="see-also"></a>Vedere anche

- [Problemi di sicurezza nella reflection emit](security-issues-in-reflection-emit.md)
- [Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox](../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
