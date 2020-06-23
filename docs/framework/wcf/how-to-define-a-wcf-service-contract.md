---
title: 'Esercitazione: definire un contratto di servizio Windows Communication Foundation'
description: Informazioni su come definire un contratto di servizio come parte di una serie di articoli che consentono di iniziare a creare un'applicazione WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246311"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Esercitazione: definire un contratto di servizio Windows Communication Foundation

In questa esercitazione viene descritta la prima delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).

Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio. Il contratto di servizio specifica le operazioni supportate dal servizio. Un'operazione può essere considerata un metodo del servizio Web. I contratti di servizio vengono creati definendo un'interfaccia C# o Visual Basic. Un'interfaccia presenta le caratteristiche seguenti:

- Ogni metodo dell'interfaccia corrisponde a un'operazione di servizio specifico.
- Per ogni interfaccia, è necessario applicare l' <xref:System.ServiceModel.ServiceContractAttribute> attributo.
- Per ogni operazione/metodo è necessario applicare l' <xref:System.ServiceModel.OperationContractAttribute> attributo.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto **libreria di servizi WCF** .
> - Definire un'interfaccia del contratto di servizio.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Creare un progetto libreria di servizi WCF e definire un'interfaccia del contratto di servizio

1. Aprire Visual Studio come amministratore. A tale scopo, selezionare il programma di Visual Studio nel menu **Start** , quindi selezionare **altro**  >  **Esegui come amministratore** dal menu di scelta rapida.

2. Creare un progetto **libreria di servizi WCF** .

   1. Scegliere **Nuovo** > **Progetto** dal menu **File**.

   2. Nella finestra di dialogo **nuovo progetto** , sul lato sinistro, espandere **Visual C#** o **Visual Basic**, quindi selezionare la categoria **WCF** . Visual Studio Visualizza un elenco di modelli di progetto nella sezione centrale della finestra. Selezionare **libreria del servizio WCF**.

      > [!NOTE]
      > Se non viene visualizzata la categoria del modello di progetto **WCF** , potrebbe essere necessario installare il componente **Windows Communication Foundation** di Visual Studio. Nella finestra di dialogo **nuovo progetto** selezionare il collegamento **Apri programma di installazione di Visual Studio** sul lato sinistro. Selezionare la scheda **singoli componenti** , quindi individuare e selezionare **Windows Communication Foundation** nella categoria **attività di sviluppo** . Scegliere **modifica** per avviare l'installazione del componente.

   3. Nella sezione inferiore della finestra immettere *GettingStartedLib* per **nome** e *GettingStarted* per il **nome della soluzione**.

   4. Selezionare **OK**.

      Visual Studio crea il progetto, che include tre file: *IService1.cs* (o *IService1. vb* per un progetto Visual Basic), *Service1.cs* (o *Service1. vb* per un progetto Visual Basic) e *App.config*. Visual Studio definisce questi file come indicato di seguito:
      - Il file *IService1* contiene la definizione predefinita del contratto di servizio.
      - Il file *Service1* contiene l'implementazione predefinita del contratto di servizio.
      - Il file di *App.config* contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento host del servizio WCF di Visual Studio. Per ulteriori informazioni sullo strumento host del servizio WCF, vedere [host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Se Visual Studio è stato installato con Visual Basic impostazioni dell'ambiente di sviluppo, la soluzione potrebbe essere nascosta. In tal caso, scegliere **Opzioni** dal menu **strumenti** , quindi scegliere **progetti e soluzioni**  >  **generale** nella finestra **Opzioni** . Selezionare **Mostra sempre soluzione**. Inoltre, verificare che l'opzione **Salva nuovi progetti al momento della creazione** sia selezionata.

3. Da **Esplora soluzioni**aprire il file **IService1.cs** o **IService1. vb** e sostituire il codice con il codice seguente:

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

     Questo contratto definisce una calcolatrice online. Si noti `ICalculator` che l'interfaccia è contrassegnata con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo (semplificato come `ServiceContract` ). Questo attributo definisce uno spazio dei nomi per evitare ambiguità nel nome del contratto. Il codice contrassegna ogni operazione del calcolatore con l' <xref:System.ServiceModel.OperationContractAttribute> attributo (semplificato come `OperationContract` ).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto libreria di servizi WCF.
> - Definire un'interfaccia del contratto di servizio.

Passare all'esercitazione successiva per apprendere come implementare il contratto di servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: implementare un contratto di servizio WCF](how-to-implement-a-wcf-contract.md)
