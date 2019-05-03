---
title: 'Procedura: Creare un servizio transazionale'
ms.date: 03/30/2017
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
ms.openlocfilehash: 7f7f060db5a4ffd66524e220e3e3291debd8a3fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787595"
---
# <a name="how-to-create-a-transactional-service"></a>Procedura: Creare un servizio transazionale
In questo esempio vengono illustrati vari aspetti della creazione di un servizio transazionale e l'utilizzo di una transazione iniziata dal client per coordinare operazioni del servizio.  
  
### <a name="creating-a-transactional-service"></a>Creazione di un servizio transazionale  
  
1. Creare un contratto di servizio e annotare le operazioni con l'impostazione desiderata dall'enumerazione <xref:System.ServiceModel.TransactionFlowOption> per specificare i requisiti della transazione in ingresso. Si noti che è anche possibile inserire <xref:System.ServiceModel.TransactionFlowAttribute> nella classe di servizio implementata. Ciò consente l'utilizzo di queste impostazioni della transazione per una singola implementazione di un'interfaccia, invece che per ogni implementazione.  
  
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
  
2. Creare una classe di implementazione e utilizzare <xref:System.ServiceModel.ServiceBehaviorAttribute> per specificare facoltativamente un <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> e un <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>. Si noti che in molti casi, l'impostazione <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> predefinita di 60 secondi e l'impostazione predefinita <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> di `Unspecified` sono appropriate. Per ogni operazione, è possibile utilizzare l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute> per specificare se il lavoro eseguito all'interno del metodo deve verificarsi all'interno dell'ambito di una transazione in base al valore dell'attributo <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>. In questo caso, la transazione utilizzata per il metodo `Add` corrisponde alla transazione in ingresso obbligatoria propagata dal client e la transazione utilizzata per il metodo `Subtract` corrisponde alla transazione in ingresso se ne è stata propagata una dal client, o a una nuova transazione creata implicitamente e localmente.  
  
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
  
3. Configurare le associazioni nel file di configurazione, specificando che il contesto della transazione deve essere propagato e i protocolli da utilizzare a tale scopo. Per altre informazioni, vedere [configurazione delle transazioni ServiceModel](servicemodel-transaction-configuration.md). In particolare, il tipo di associazione è specificato nell'attributo `binding` dell'elemento endpoint. Il [ \<endpoint >](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento contiene un `bindingConfiguration` attributo che fa riferimento a una configurazione di associazione denominata `transactionalOleTransactionsTcpBinding`, come illustrato nell'esempio di configurazione seguente.  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     Il flusso delle transazioni viene attivato a livello di configurazione utilizzando l'attributo `transactionFlow` e il protocollo della transazione viene specificato utilizzando l'attributo `transactionProtocol`, come illustrato nella configurazione seguente.  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a>Supporto di più protocolli di transazione  
  
1. Per ottenere prestazioni ottimali, è necessario usare il protocollo OleTransactions per scenari che prevedono un client e servizio scritto utilizzando Windows Communication Foundation (WCF). Il protocollo WS-AtomicTransaction (WS-AT), tuttavia, è utile per scenari in cui è richiesta l'interoperabilità con stack del protocollo di terze parti. È possibile configurare servizi WCF per accettare entrambi protocolli fornendo più endpoint con associazioni appropriate specifiche del protocollo, come illustrato nell'esempio di configurazione seguente.  
  
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
  
     Il protocollo di transazione viene specificato utilizzando l'attributo `transactionProtocol`. Questo attributo è tuttavia assente dal `wsHttpBinding` fornito dal sistema perché questa associazione può utilizzare solo il protocollo WS-AT.  
  
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
  
### <a name="controlling-the-completion-of-a-transaction"></a>Controllo del completamento di una transazione  
  
1. Per impostazione predefinita, le operazioni WCF completano automaticamente le transazioni se non vengono generate eccezioni gestite. È possibile modificare questo comportamento utilizzando la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> e il metodo <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>. Quando è necessario che un'operazione si verifichi all'interno della stessa transazione di un'altra operazione (ad esempio, un'operazione di addebito e di accredito), è possibile disattivare il comportamento di completamento automatico impostando la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> su `false`, come illustrato nell'esempio dell'operazione `Debit` seguente. La transazione utilizzata dall'operazione `Debit` non viene completata finché non viene chiamato un metodo con la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> impostata su `true`, come illustrato nell'operazione `Credit1` o finché non viene chiamato il metodo <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> per contrassegnare in modo esplicito la transazione come completata, come illustrato nell'operazione `Credit2`. Si noti che le due operazioni di accredito sono riportate a solo scopo illustrativo e che una singola operazione sarebbe più tipica.  
  
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
  
2. Ai fini della correlazione delle transazioni, per impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> su `false` è richiesto l'utilizzo di un'associazione con sessione. Questo requisito è specificato con la proprietà `SessionMode` in <xref:System.ServiceModel.ServiceContractAttribute>.  
  
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
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a>Controllo della durata di un'istanza del servizio transazionale  
  
1. WCF utilizza il <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> proprietà per specificare se l'istanza del servizio sottostante viene rilasciata al completamento di una transazione. Poiché il valore predefinito è `true`, a meno che non configurato in caso contrario, il comportamento di attivazione di WCF esposizioni un'efficiente e prevedibile "just-in-time". Alle chiamate a un servizio in una transazione successiva viene assicurata una nuova istanza del servizio, senza resti dello stato della transazione precedente. Anche se ciò è spesso utile, qualche volta è necessario mantenere lo stato all'interno dell'istanza del servizio oltre il completamento della transazione, ad esempio quando è oneroso recuperare o ricostruire lo stato richiesto o gli handle di risorse. A tale fine, impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> su `false`. Grazie a tale impostazione, l'istanza e qualsiasi stato associato saranno disponibili alle chiamate successive. In tal caso, valutare attentamente quando e come lo stato e le transazioni verranno cancellati e completati. Nell'esempio seguente viene illustrato come procedere gestendo l'istanza con la variabile `runningTotal`.  
  
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
    >  Poiché la durata dell'istanza è un comportamento interno al servizio e viene controllato tramite la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute>, per impostare il comportamento dell'istanza non è richiesta alcuna modifica alla configurazione del servizio o al contratto di servizio. La rete non conterrà inoltre nessuna rappresentazione di tale situazione.
