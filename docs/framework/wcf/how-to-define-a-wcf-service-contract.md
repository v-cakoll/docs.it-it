---
title: 'Esercitazione: Definire un contratto di servizio di Windows Communication FoundationTutorial: Define a Windows Communication Foundation service contract'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184089"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Esercitazione: Definire un contratto di servizio di Windows Communication FoundationTutorial: Define a Windows Communication Foundation service contract

Questa esercitazione descrive la prima delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base. Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio. Il contratto di servizio specifica le operazioni supportate dal servizio. Un'operazione può essere considerata un metodo del servizio Web. È possibile creare contratti di servizio definendo un'interfaccia di C o Visual Basic. Un'interfaccia ha le seguenti caratteristiche:

- Ogni metodo dell'interfaccia corrisponde a un'operazione di servizio specifico.
- Per ogni interfaccia, è <xref:System.ServiceModel.ServiceContractAttribute> necessario applicare l'attributo.
- Per ogni operazione/metodo, è <xref:System.ServiceModel.OperationContractAttribute> necessario applicare l'attributo.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto **libreria di servizi WCF.**
> - Definire un'interfaccia del contratto di servizio.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Creare un progetto di libreria di servizi WCF e definire un'interfaccia del contratto di servizioCreate a WCF Service Library project and define a service contract interface

1. Aprire Visual Studio come amministratore. A tale scopo, selezionare il programma di Visual Studio nel menu **Start** e quindi selezionare **Altro** > **Esegui come amministratore** dal menu di scelta rapida.

2. Creare un progetto **libreria di servizi WCF.**

   1. Scegliere **Nuovo** > **Progetto** dal menu **File**.

   2. Nella finestra di dialogo **Nuovo progetto,** sul lato sinistro, espandere **Visual C,** o **Visual Basic**, quindi selezionare la categoria **WCF.** Visual Studio visualizza un elenco di modelli di progetto nella sezione centrale della finestra. Selezionare **Libreria di servizi WCF**.

      > [!NOTE]
      > Se la categoria del modello di progetto WCF non è visualizzata, potrebbe essere necessario installare il componente Windows Communication Foundation di Visual Studio.If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio. Nella finestra di dialogo **Nuovo progetto** selezionare il collegamento Apri programma di installazione di **Visual Studio** sul lato sinistro. Selezionare la scheda **Singoli componenti,** quindi individuare e selezionare **Windows Communication Foundation** nella categoria Attività di **sviluppo.** Scegliere **Modifica** per avviare l'installazione del componente.

   3. Nella sezione inferiore della finestra immettere *GettingStartedLib* come **Nome** e *GettingStarted* come **Nome soluzione**.

   4. Selezionare **OK**.

      Visual Studio crea il progetto, che dispone di tre file: *IService1.cs* (o *IService1.vb* per un progetto Visual Basic), *Service1.cs* (o *Service1.vb* per un progetto Visual Basic) e *App.config*. Visual Studio definisce questi file come segue:Visual Studio defines these files as follows:
      - Il file *IService1* contiene la definizione predefinita del contratto di servizio.
      - Il file *Service1* contiene l'implementazione predefinita del contratto di servizio.
      - Il file App.config contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento Host del servizio WCF di Visual Studio.The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool. Per ulteriori informazioni sullo strumento Host servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Se è stato installato Visual Studio con le impostazioni dell'ambiente di sviluppo visual Basic, la soluzione potrebbe essere nascosta. In questo caso, selezionare **Opzioni** dal menu **Strumenti,** quindi selezionare **Progetti e soluzioni** > **generali** nella finestra **Opzioni.** Selezionare **Mostra sempre soluzione**. Verificare inoltre che **l'opzione Salva nuovi progetti al momento della creazione** sia selezionata.

3. In **Esplora soluzioni**aprire il file **IService1.cs** o **IService1.vb** e sostituirne il codice con il codice seguente:

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

     Questo contratto definisce una calcolatrice online. Si `ICalculator` noti che <xref:System.ServiceModel.ServiceContractAttribute> l'interfaccia `ServiceContract`è contrassegnata con l'attributo (semplificato come ). Questo attributo definisce uno spazio dei nomi per evitare ambiguità nel nome del contratto. Il codice contrassegna ogni <xref:System.ServiceModel.OperationContractAttribute> operazione della `OperationContract`calcolatrice con l'attributo (semplificato come ).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto libreria di servizi WCF.
> - Definire un'interfaccia del contratto di servizio.

Passare all'esercitazione successiva per informazioni su come implementare il contratto di servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Implementare un contratto di servizio WCFTutorial: Implement a WCF service contract](how-to-implement-a-wcf-contract.md)
