---
title: 'Procedura: Creare un servizio transazionale'
ms.date: 03/30/2017
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
ms.openlocfilehash: be364e7638394a30c199b05dd15ef4c44e18e688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964011"
---
# <a name="how-to-create-a-transactional-service"></a><span data-ttu-id="51e48-102">Procedura: Creare un servizio transazionale</span><span class="sxs-lookup"><span data-stu-id="51e48-102">How to: Create a Transactional Service</span></span>
<span data-ttu-id="51e48-103">In questo esempio vengono illustrati vari aspetti della creazione di un servizio transazionale e l'utilizzo di una transazione iniziata dal client per coordinare operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="51e48-103">This sample demonstrates various aspects of creating a transactional service and the use of a client-initiated transaction to coordinate service operations.</span></span>  
  
### <a name="creating-a-transactional-service"></a><span data-ttu-id="51e48-104">Creazione di un servizio transazionale</span><span class="sxs-lookup"><span data-stu-id="51e48-104">Creating a transactional service</span></span>  
  
1. <span data-ttu-id="51e48-105">Creare un contratto di servizio e annotare le operazioni con l'impostazione desiderata dall'enumerazione <xref:System.ServiceModel.TransactionFlowOption> per specificare i requisiti della transazione in ingresso.</span><span class="sxs-lookup"><span data-stu-id="51e48-105">Create a service contract and annotate the operations with the desired setting from the <xref:System.ServiceModel.TransactionFlowOption> enumeration to specify the incoming transaction requirements.</span></span> <span data-ttu-id="51e48-106">Si noti che è anche possibile inserire <xref:System.ServiceModel.TransactionFlowAttribute> nella classe di servizio implementata.</span><span class="sxs-lookup"><span data-stu-id="51e48-106">Note that you can also place the <xref:System.ServiceModel.TransactionFlowAttribute> on the service class being implemented.</span></span> <span data-ttu-id="51e48-107">Ciò consente l'utilizzo di queste impostazioni della transazione per una singola implementazione di un'interfaccia, invece che per ogni implementazione.</span><span class="sxs-lookup"><span data-stu-id="51e48-107">This allows for a single implementation of an interface to use these transaction settings, instead of every implementation.</span></span>  
  
    ```csharp
    [ServiceContract]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // Use this to require an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Mandatory)]  
        double Add(double n1, double n2);  
        [OperationContract]  
        // Use this to permit an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        double Subtract(double n1, double n2);  
    }  
    ```  
  
2. <span data-ttu-id="51e48-108">Creare una classe di implementazione e utilizzare <xref:System.ServiceModel.ServiceBehaviorAttribute> per specificare facoltativamente un <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> e un <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="51e48-108">Create an implementation class, and use the <xref:System.ServiceModel.ServiceBehaviorAttribute> to optionally specify a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span></span> <span data-ttu-id="51e48-109">Si noti che in molti casi, l'impostazione <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> predefinita di 60 secondi e l'impostazione predefinita <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> di `Unspecified` sono appropriate.</span><span class="sxs-lookup"><span data-stu-id="51e48-109">You should note that in many cases, the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> of 60 seconds and the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> of `Unspecified` are appropriate.</span></span> <span data-ttu-id="51e48-110">Per ogni operazione, è possibile utilizzare l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute> per specificare se il lavoro eseguito all'interno del metodo deve verificarsi all'interno dell'ambito di una transazione in base al valore dell'attributo <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>.</span><span class="sxs-lookup"><span data-stu-id="51e48-110">For each operation, you can use the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute to specify whether work performed within the method should occur within the scope of a transaction scope according to the value of the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> attribute.</span></span> <span data-ttu-id="51e48-111">In questo caso, la transazione utilizzata per il metodo `Add` corrisponde alla transazione in ingresso obbligatoria propagata dal client e la transazione utilizzata per il metodo `Subtract` corrisponde alla transazione in ingresso se ne è stata propagata una dal client, o a una nuova transazione creata implicitamente e localmente.</span><span class="sxs-lookup"><span data-stu-id="51e48-111">In this case, the transaction used for the `Add` method is the same as the mandatory incoming transaction that is flowed from the client, and the transaction used for the `Subtract` method is either the same as the incoming transaction if one was flowed from the client, or a new implicitly and locally created transaction.</span></span>  
  
    ```csharp
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n1} to {n2}");
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n2} from {n1}");
            return n1 - n2;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
            // This is where the transaction provides specific benefit  
            // - changes to the database will be committed only when  
            // the transaction completes.  
        }  
    }  
    ```  
  
3. <span data-ttu-id="51e48-112">Configurare le associazioni nel file di configurazione, specificando che il contesto della transazione deve essere propagato e i protocolli da utilizzare a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="51e48-112">Configure the bindings in the configuration file, specifying that the transaction context should be flowed, and the protocols to be used to do so.</span></span> <span data-ttu-id="51e48-113">Per ulteriori informazioni, vedere la pagina relativa alla [configurazione delle transazioni ServiceModel](servicemodel-transaction-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="51e48-113">For more information, see [ServiceModel Transaction Configuration](servicemodel-transaction-configuration.md).</span></span> <span data-ttu-id="51e48-114">In particolare, il tipo di associazione è specificato nell'attributo `binding` dell'elemento endpoint.</span><span class="sxs-lookup"><span data-stu-id="51e48-114">Specifically, the binding type is specified in the endpoint element’s `binding` attribute.</span></span> <span data-ttu-id="51e48-115">L'elemento [ \<> dell'endpoint](../../configure-apps/file-schema/wcf/endpoint-element.md) contiene un `bindingConfiguration` attributo che fa riferimento a una `transactionalOleTransactionsTcpBinding`configurazione di associazione denominata, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51e48-115">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element contains a `bindingConfiguration` attribute that references a binding configuration named `transactionalOleTransactionsTcpBinding`, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="51e48-116">Il flusso delle transazioni viene attivato a livello di configurazione utilizzando l'attributo `transactionFlow` e il protocollo della transazione viene specificato utilizzando l'attributo `transactionProtocol`, come illustrato nella configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="51e48-116">Transaction flow is enabled at the configuration level by using the `transactionFlow` attribute, and the transaction protocol is specified using the `transactionProtocol` attribute, as shown in the following configuration.</span></span>  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a><span data-ttu-id="51e48-117">Supporto di più protocolli di transazione</span><span class="sxs-lookup"><span data-stu-id="51e48-117">Supporting multiple transaction protocols</span></span>  
  
1. <span data-ttu-id="51e48-118">Per ottenere prestazioni ottimali, è consigliabile utilizzare il protocollo OleTransactions per gli scenari che coinvolgono un client e un servizio scritto utilizzando Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="51e48-118">For optimal performance, you should use the OleTransactions protocol for scenarios involving a client and service written using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="51e48-119">Il protocollo WS-AtomicTransaction (WS-AT), tuttavia, è utile per scenari in cui è richiesta l'interoperabilità con stack del protocollo di terze parti.</span><span class="sxs-lookup"><span data-stu-id="51e48-119">However, the WS-AtomicTransaction (WS-AT) protocol is useful for scenarios when interoperability with third-party protocol stacks is required.</span></span> <span data-ttu-id="51e48-120">È possibile configurare i servizi WCF in modo che accettino entrambi i protocolli fornendo più endpoint con binding appropriati specifici del protocollo, come illustrato nella configurazione di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="51e48-120">You can configure WCF services to accept both protocols by providing multiple endpoints with appropriate protocol-specific bindings, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="http://localhost:8000/CalcService"  
        binding="wsHttpBinding"  
        bindingConfiguration="transactionalWsatHttpBinding"  
        contract="ICalculator"  
        name="WSAtomicTransaction_endpoint" />  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="51e48-121">Il protocollo di transazione viene specificato utilizzando l'attributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="51e48-121">The transaction protocol is specified using the `transactionProtocol` attribute.</span></span> <span data-ttu-id="51e48-122">Questo attributo è tuttavia assente dal `wsHttpBinding` fornito dal sistema perché questa associazione può utilizzare solo il protocollo WS-AT.</span><span class="sxs-lookup"><span data-stu-id="51e48-122">However, this attribute is absent from the system-provided `wsHttpBinding`, because this binding can only use the WS-AT protocol.</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
        <binding name="transactionalWsatHttpBinding"  
          transactionFlow="true" />  
      </wsHttpBinding>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="controlling-the-completion-of-a-transaction"></a><span data-ttu-id="51e48-123">Controllo del completamento di una transazione</span><span class="sxs-lookup"><span data-stu-id="51e48-123">Controlling the completion of a transaction</span></span>  
  
1. <span data-ttu-id="51e48-124">Per impostazione predefinita, le operazioni WCF completano automaticamente le transazioni se non vengono generate eccezioni non gestite.</span><span class="sxs-lookup"><span data-stu-id="51e48-124">By default, WCF operations automatically complete transactions if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="51e48-125">È possibile modificare questo comportamento utilizzando la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> e il metodo <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="51e48-125">You can modify this behavior by using the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property and the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method.</span></span> <span data-ttu-id="51e48-126">Quando è necessario che un'operazione si verifichi all'interno della stessa transazione di un'altra operazione (ad esempio, un'operazione di addebito e di accredito), è possibile disattivare il comportamento di completamento automatico impostando la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> su `false`, come illustrato nell'esempio dell'operazione `Debit` seguente.</span><span class="sxs-lookup"><span data-stu-id="51e48-126">When an operation is required to occur within the same transaction as another operation (for example, a debit and credit operation), you can disable the autocomplete behavior by setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` as shown in the following `Debit` operation example.</span></span> <span data-ttu-id="51e48-127">La transazione utilizzata dall'operazione `Debit` non viene completata finché non viene chiamato un metodo con la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> impostata su `true`, come illustrato nell'operazione `Credit1` o finché non viene chiamato il metodo <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> per contrassegnare in modo esplicito la transazione come completata, come illustrato nell'operazione `Credit2`.</span><span class="sxs-lookup"><span data-stu-id="51e48-127">The transaction the `Debit` operation uses is not completed until a method with the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property set to `true` is called, as shown in the operation `Credit1`, or when the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method is called to explicitly mark the transaction as complete, as shown in the operation `Credit2`.</span></span> <span data-ttu-id="51e48-128">Si noti che le due operazioni di accredito sono riportate a solo scopo illustrativo e che una singola operazione sarebbe più tipica.</span><span class="sxs-lookup"><span data-stu-id="51e48-128">Note that the two credit operations are shown for illustration purposes, and that a single credit operation would be more typical.</span></span>  
  
    ```csharp
    [ServiceBehavior]  
    public class CalculatorService : IAccount  
    {  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Debit(double n)  
        {  
            // Perform debit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void Credit1(double n)  
        {  
            // Perform credit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Credit2(double n)  
        {  
            // Perform alternate credit operation  
  
            OperationContext.Current.SetTransactionComplete();  
            return;  
        }  
    }  
    ```  
  
2. <span data-ttu-id="51e48-129">Ai fini della correlazione delle transazioni, per impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> su `false` è richiesto l'utilizzo di un'associazione con sessione.</span><span class="sxs-lookup"><span data-stu-id="51e48-129">For the purposes of transaction correlation, setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` requires the use of a sessionful binding.</span></span> <span data-ttu-id="51e48-130">Questo requisito è specificato con la proprietà `SessionMode` in <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="51e48-130">This requirement is specified with the `SessionMode` property on the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span>  
  
    ```csharp
    [ServiceContract(SessionMode = SessionMode.Required)]  
    public interface IAccount  
    {  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Debit(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit1(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit2(double n);  
    }  
    ```  
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a><span data-ttu-id="51e48-131">Controllo della durata di un'istanza del servizio transazionale</span><span class="sxs-lookup"><span data-stu-id="51e48-131">Controlling the lifetime of a transactional service instance</span></span>  
  
1. <span data-ttu-id="51e48-132">WCF utilizza la <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> proprietà per specificare se l'istanza del servizio sottostante viene rilasciata al completamento di una transazione.</span><span class="sxs-lookup"><span data-stu-id="51e48-132">WCF uses the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to specify whether the underlying service instance is released when a transaction completes.</span></span> <span data-ttu-id="51e48-133">Poiché il valore predefinito è `true`, a meno che non sia configurato diversamente, WCF presenta un comportamento di attivazione "just-in-Time" efficiente e prevedibile.</span><span class="sxs-lookup"><span data-stu-id="51e48-133">Since this defaults to `true`, unless configured otherwise, WCF exhibits an efficient and predictable "just-in-time" activation behavior.</span></span> <span data-ttu-id="51e48-134">Alle chiamate a un servizio in una transazione successiva viene assicurata una nuova istanza del servizio, senza resti dello stato della transazione precedente.</span><span class="sxs-lookup"><span data-stu-id="51e48-134">Calls to a service on a subsequent transaction are assured a new service instance with no remnants of the previous transaction's state.</span></span> <span data-ttu-id="51e48-135">Anche se ciò è spesso utile, qualche volta è necessario mantenere lo stato all'interno dell'istanza del servizio oltre il completamento della transazione,</span><span class="sxs-lookup"><span data-stu-id="51e48-135">While this is often useful, sometimes you may want to maintain state within the service instance beyond the transaction completion.</span></span> <span data-ttu-id="51e48-136">ad esempio quando è oneroso recuperare o ricostruire lo stato richiesto o gli handle di risorse.</span><span class="sxs-lookup"><span data-stu-id="51e48-136">Examples of this would be when required state or handles to resources are expensive to retrieve or reconstitute.</span></span> <span data-ttu-id="51e48-137">A tale fine, impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="51e48-137">You can do this by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to `false`.</span></span> <span data-ttu-id="51e48-138">Grazie a tale impostazione, l'istanza e qualsiasi stato associato saranno disponibili alle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="51e48-138">With that setting, the instance and any associated state will be available on subsequent calls.</span></span> <span data-ttu-id="51e48-139">In tal caso, valutare attentamente quando e come lo stato e le transazioni verranno cancellati e completati.</span><span class="sxs-lookup"><span data-stu-id="51e48-139">When using this, give careful consideration to when and how state and transactions will be cleared and completed.</span></span> <span data-ttu-id="51e48-140">Nell'esempio seguente viene illustrato come procedere gestendo l'istanza con la variabile `runningTotal`.</span><span class="sxs-lookup"><span data-stu-id="51e48-140">The following sample demonstrates how to do this by maintaining the instance with the `runningTotal` variable.</span></span>  
  
    ```csharp
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n} to {runningTotal}");
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n} from {runningTotal}");
            runningTotal = runningTotal - n;  
            return runningTotal;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
        }  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="51e48-141">Poiché la durata dell'istanza è un comportamento interno al servizio e viene controllato tramite la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute>, per impostare il comportamento dell'istanza non è richiesta alcuna modifica alla configurazione del servizio o al contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="51e48-141">Since the instance lifetime is a behavior that is internal to the service, and controlled through the <xref:System.ServiceModel.ServiceBehaviorAttribute> property, no modification to the service configuration or service contract is required to set the instance behavior.</span></span> <span data-ttu-id="51e48-142">La rete non conterrà inoltre nessuna rappresentazione di tale situazione.</span><span class="sxs-lookup"><span data-stu-id="51e48-142">In addition, the wire will contain no representation of this.</span></span>
