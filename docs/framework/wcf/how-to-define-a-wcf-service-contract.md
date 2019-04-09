---
title: 'Esercitazione: Definire un contratto di servizio Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228393"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Esercitazione: Definire un contratto di servizio Windows Communication Foundation

Questa esercitazione illustra il primo di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).

Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio. Nel contratto di servizio vengono specificate le operazioni supportate dal servizio. Un'operazione può essere considerata un metodo del servizio Web. Per creare i contratti di servizio necessario definire un oggetto visivo C# o l'interfaccia di Visual Basic (VB). Un'interfaccia presenta le caratteristiche seguenti:

- Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica. 
- Per ogni interfaccia, è necessario applicare il <xref:System.ServiceModel.ServiceContractAttribute> attributo.
- Per ogni operazione o metodo, è necessario applicare il <xref:System.ServiceModel.OperationContractAttribute> attributo. 

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> - Creare un **WCF Service Library** progetto.
> - Definire un'interfaccia del contratto di servizio.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Creare un progetto libreria di servizi WCF e definire un'interfaccia del contratto di servizio

1. Aprire Visual Studio come amministratore. A tale scopo, selezionare il programma in Visual Studio il **avviare** menu e quindi selezionare **ulteriori** > **Esegui come amministratore** dal menu di scelta rapida.

2. Creare un **WCF Service Library** progetto.

   1. Scegliere **Nuovo** > **Progetto** dal menu **File**.

   2. Nel **nuovo progetto** finestra di dialogo sul lato sinistro, espandere **Visual c#** oppure **Visual Basic**e quindi selezionare il **WCF** categoria. Visual Studio visualizza un elenco di modelli di progetto nella sezione centrale della finestra. Selezionare **WCF Service Library**.

      > [!NOTE]
      > Se non viene visualizzato il **WCF** categoria di modelli di progetto, potrebbe essere necessario installare il **Windows Communication Foundation** componente di Visual Studio. Nel **nuovo progetto** finestra di dialogo, seleziona la **aperto Visual Studio Installer** collegamento sul lato sinistro. Selezionare il **singoli componenti** scheda e quindi cercare e selezionare **Windows Communication Foundation** sotto il **le attività di sviluppo** categoria. Scegli **Modify** per iniziare a installare il componente.

   3. Nella parte inferiore della finestra, immettere *GettingStartedLib* per il **Name** e *GettingStarted* per il **Nome soluzione**. 

   4. Scegliere **OK**.

      Visual Studio crea il progetto che dispone di tre file: *IService1.cs* (o *IService1.vb* per un progetto Visual Basic), *Service1.cs* (o *Service1.vb* per un progetto Visual Basic), e  *App. config*. Visual Studio definisce questi file come indicato di seguito: 
      - Il *IService1* file contiene la definizione predefinita del contratto di servizio. 
      - Il *Service1* file contiene l'implementazione predefinita del contratto di servizio. 
      - Il *app. config* file contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento Host del servizio WCF di Visual Studio. Per altre informazioni sullo strumento Host del servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Se è installato Visual Studio con le impostazioni di ambiente per gli sviluppatori Visual Basic, la soluzione potrebbe essere nascosta. In questo caso, selezionare **opzioni** dal **Tools** menu, quindi selezionare **progetti e soluzioni** > **generale** in il **opzioni** finestra. Selezionare **Mostra sempre soluzione**. Inoltre, verificare che **Salva nuovi progetti alla creazione** sia selezionata.

3. Dal **Esplora soluzioni**, aprire il **IService1.cs** oppure **IService1.vb** file e sostituire il codice con il codice seguente:

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

     Questo contratto definisce una calcolatrice online. Si noti che il `ICalculator` interfaccia è contrassegnata con il <xref:System.ServiceModel.ServiceContractAttribute> attributo (semplificata come `ServiceContract`). Questo attributo definisce uno spazio dei nomi per evitare ambiguità tra il nome del contratto. Il codice contrassegna ogni operazione della calcolatrice con il <xref:System.ServiceModel.OperationContractAttribute> attributo (semplificata come `OperationContract`).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> - Creare un progetto libreria di servizi WCF.
> - Definire un'interfaccia del contratto di servizio.

Passare all'esercitazione successiva per informazioni su come implementare il contratto di servizio WCF.

> [!div class="nextstepaction"]
> [Esercitazione: Implementare un contratto di servizio WCF](how-to-implement-a-wcf-contract.md)
