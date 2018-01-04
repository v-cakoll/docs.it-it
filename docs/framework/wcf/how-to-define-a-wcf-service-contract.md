---
title: 'Procedura: definire un contratto di servizio di Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: "58"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c69f79d8629acee80a2e59346032e7733ec37dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Procedura: definire un contratto di servizio di Windows Communication Foundation
Questa è la prima delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] di base. Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.  
  
 Quando si crea un servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la prima attività consiste nel definire un contratto di servizio. Nel contratto di servizio vengono specificate le operazioni supportate dal servizio. Un'operazione può essere considerata un metodo del servizio Web. I contratti vengono creati definendo un'interfaccia C++, C# o Visual Basic (VB). Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica. A ogni interfaccia deve essere applicato l'oggetto <xref:System.ServiceModel.ServiceContractAttribute> e a ogni operazione deve essere applicato l'attributo <xref:System.ServiceModel.OperationContractAttribute>. Se un metodo di un'interfaccia a cui è associato l'attributo <xref:System.ServiceModel.ServiceContractAttribute> non dispone dell'attributo <xref:System.ServiceModel.OperationContractAttribute>, tale metodo non viene esposto dal servizio.  
  
 Nell'esempio riportato dopo la procedura, viene fornito il codice utilizzato per questa attività.  
  
### <a name="to-define-a-service-contract"></a>Per definire un contratto di servizio  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] come amministratore facendo clic con il programma di **avviare** menu e selezionando **Esegui come amministratore**.  
  
2.  Creare un progetto libreria di servizi WCF facendo il **File** menu e selezionando **New**, **progetto**. Nel **nuovo progetto** finestra di dialogo, sul lato sinistro della finestra di dialogo espandere **Visual c#** per un progetto c# o **altri linguaggi** e quindi **diVisualBasic** per un progetto di Visual Basic. Selezionare la lingua selezionata **WCF** e verrà visualizzato un elenco di modelli di progetto nella sezione centrale della finestra di dialogo. Selezionare **libreria di servizi WCF**e il tipo `GettingStartedLib` nel **nome** casella di testo e `GettingStarted` nel **Nome soluzione** casella di testo nella parte inferiore della finestra di dialogo.  
  
3.  Visual Studio creerà il progetto che contiene 3 file: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) e App.config.  Il file IService1 contiene un contratto di servizio predefinito.  Il file Service1 contiene un'implementazione predefinita del contratto di servizio. Il file App.config contiene la configurazione necessaria per caricare il servizio predefinito con l'host del servizio WCF di Visual Studio. Per ulteriori informazioni sullo strumento di Host servizio WCF, vedere [Host servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
4.  Aprire il file IService1.cs o IService1.vb ed eliminare il codice all'interno della dichiarazione dello spazio dei nomi mantenendo però quest'ultima. All'interno della dichiarazione dello spazio dei nomi definire una nuova interfaccia denominata `ICalculator`, come mostrato nel codice seguente.  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
            public interface ICalculator  
            {  
                [OperationContract]  
                double Add(double n1, double n2);  
                [OperationContract]  
                double Subtract(double n1, double n2);  
                [OperationContract]  
                double Multiply(double n1, double n2);  
                [OperationContract]  
                double Divide(double n1, double n2);  
            }  
    }  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
    ```  
  
     Questo contratto definisce una calcolatrice online. Si noti che l'interfaccia `ICalculator` è contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute>. Questo attributo definisce uno spazio dei nomi utilizzato per evitare ambiguità nel nome del contratto. Ogni operazione della calcolatrice è contrassegnata con l'attributo <xref:System.ServiceModel.OperationContractAttribute>.  
  
    > [!NOTE]
    >  Quando vengono utilizzati attributi per annotare un'interfaccia, un membro o una classe, è possibile eliminare la parte "Attribute" dal nome dell'attributo. In questo modo <xref:System.ServiceModel.ServiceContractAttribute> diventa `[ServiceContract]` in C# o `<ServiceContract>` in Visual Basic.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Procedura: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
