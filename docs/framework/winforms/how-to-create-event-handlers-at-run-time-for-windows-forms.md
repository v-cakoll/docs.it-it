---
title: 'Procedura: creare gestori eventi in fase di esecuzione'
description: Informazioni su come creare un gestore eventi in fase di esecuzione con il Progettazione Windows Form in Visual Studio. Questa azione consente di connettere i gestori eventi in fase di esecuzione.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 857076c46377b3276154d9b193d4bbe51841828f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325802"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="16f4e-104">Procedura: Creare gestori eventi in fase di esecuzione per Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16f4e-104">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="16f4e-105">Oltre a creare eventi usando il Progettazione Windows Form in Visual Studio, è anche possibile creare un gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="16f4e-105">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="16f4e-106">Questa azione consente di connettere i gestori eventi in base alle condizioni nel codice in fase di esecuzione invece di connetterli all'avvio iniziale del programma.</span><span class="sxs-lookup"><span data-stu-id="16f4e-106">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="16f4e-107">Creare un gestore eventi in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="16f4e-107">Create an event handler at run time</span></span>

1. <span data-ttu-id="16f4e-108">Aprire il modulo a cui si desidera aggiungere un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="16f4e-108">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="16f4e-109">Aggiungere un metodo al modulo con la firma del metodo per l'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="16f4e-109">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="16f4e-110">Se, ad esempio, si stava gestendo l' <xref:System.Windows.Forms.Control.Click> evento di un <xref:System.Windows.Forms.Button> controllo, si creerebbe un metodo come il seguente:</span><span class="sxs-lookup"><span data-stu-id="16f4e-110">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. <span data-ttu-id="16f4e-111">Aggiungere un codice al gestore dell'evento appropriato per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="16f4e-111">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="16f4e-112">Stabilire per quale modulo o controllo si desidera creare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="16f4e-112">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="16f4e-113">In un metodo nella classe del modulo, aggiungere il codice che specifica il gestore eventi per gestire l'evento.</span><span class="sxs-lookup"><span data-stu-id="16f4e-113">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="16f4e-114">Ad esempio, il codice seguente specifica che il gestore eventi `button1_Click` gestisce l' <xref:System.Windows.Forms.Control.Click> evento di un <xref:System.Windows.Forms.Button> controllo:</span><span class="sxs-lookup"><span data-stu-id="16f4e-114">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="16f4e-115">Il <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> metodo illustrato nel codice Visual Basic precedente stabilisce un gestore dell'evento click per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="16f4e-115">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="16f4e-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="16f4e-116">See also</span></span>

- [<span data-ttu-id="16f4e-117">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="16f4e-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="16f4e-118">Panoramica sui gestori eventi</span><span class="sxs-lookup"><span data-stu-id="16f4e-118">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="16f4e-119">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16f4e-119">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
