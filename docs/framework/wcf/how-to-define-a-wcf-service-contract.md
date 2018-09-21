---
title: 'Procedura: definire un contratto di servizio di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537878"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Procedura: definire un contratto di servizio di Windows Communication Foundation

Questa è la prima delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).

 Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio. Nel contratto di servizio vengono specificate le operazioni supportate dal servizio. Un'operazione può essere considerata un metodo del servizio Web. I contratti vengono creati definendo un'interfaccia C++, C# o Visual Basic (VB). Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica. A ogni interfaccia deve essere applicato l'oggetto <xref:System.ServiceModel.ServiceContractAttribute> e a ogni operazione deve essere applicato l'attributo <xref:System.ServiceModel.OperationContractAttribute>. Se un metodo di un'interfaccia a cui è associato l'attributo <xref:System.ServiceModel.ServiceContractAttribute> non dispone dell'attributo <xref:System.ServiceModel.OperationContractAttribute>, tale metodo non viene esposto dal servizio.

 Nell'esempio riportato dopo la procedura, viene fornito il codice utilizzato per questa attività.

## <a name="define-a-service-contract"></a>Definire un contratto di servizio

1. Aprire Visual Studio come amministratore facendo clic con il programma nel **avviare** dal menu e selezionando **ulteriori** > **Esegui come amministratore**.

2. Creare un progetto libreria di servizi WCF.

   1. Scegliere **Nuovo** > **Progetto** dal menu **File**.

   2. Nel **nuovo progetto** finestra di dialogo sul lato sinistro, espandere **Visual c#** oppure **Visual Basic**e quindi selezionare il **WCF** categoria. Nella sezione centrale della finestra di dialogo viene visualizzato un elenco di modelli di progetto. Selezionare **WCF Service Library**.

   3. Immettere `GettingStartedLib` nella **Name** nella casella di testo e `GettingStarted` nel **Nome soluzione** nella casella di testo nella parte inferiore della finestra di dialogo.

   > [!NOTE]
   > Se non viene visualizzato il **WCF** categoria di modelli di progetto, potrebbe essere necessario installare il **Windows Communication Foundation** componente di Visual Studio. Nel **nuovo progetto** finestra di dialogo, scegliere il collegamento con la dicitura **aperto Visual Studio Installer**. Selezionare il **singoli componenti** scheda e quindi cercare e selezionare **Windows Communication Foundation** sotto il **le attività di sviluppo** categoria. Scegli **Modify** per iniziare a installare il componente.

   Visual Studio crea il progetto che contiene 3 file: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) e App. config. Il file IService1 contiene un contratto di servizio predefinito. Il file Service1 contiene un'implementazione predefinita del contratto di servizio. Il file App.config contiene la configurazione necessaria per caricare il servizio predefinito con l'host del servizio WCF di Visual Studio. Per altre informazioni sullo strumento Host del servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

3. Aprire il file IService1.cs o IService1.vb ed eliminare il codice all'interno della dichiarazione dello spazio dei nomi, lasciando la dichiarazione dello spazio dei nomi. All'interno della dichiarazione dello spazio dei nomi definire una nuova interfaccia denominata `ICalculator`, come mostrato nel codice seguente.

    ```csharp
    using System;
    using System.ServiceModel;

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

    ```vb
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

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Procedura: implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Procedura: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)