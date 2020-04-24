---
title: 'Procedura: chiamare un servizio Web in modo asincrono'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: d288cc1f2991a8f504dc9f1b206bba76fa378b75
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76794557"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="3766d-102">Procedura: chiamare un servizio Web in modo asincrono (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3766d-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>

<span data-ttu-id="3766d-103">Questo esempio associa un gestore a un evento gestore asincrono di un servizio Web in modo che possa recuperare il risultato di una chiamata di metodo sincrono.</span><span class="sxs-lookup"><span data-stu-id="3766d-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="3766d-104">L'esempio usa il servizio Web DemoTemperatureService disponibile all'indirizzo `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="3766d-104">This example used the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span>

<span data-ttu-id="3766d-105">Quando in un progetto si fa riferimento a un servizio Web nell'ambiente di sviluppo integrato (IDE, Integrated Development Environment) di Visual Studio, questo viene aggiunto all'oggetto `My.WebServices` e l'IDE genera una classe proxy del client per accedere a un servizio Web specifico</span><span class="sxs-lookup"><span data-stu-id="3766d-105">When you reference a Web service in your project in the Visual Studio Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>

<span data-ttu-id="3766d-106">La classe proxy consente di chiamare i metodi del servizio Web in modo sincrono; in altre parole l'applicazione aspetta che la funzione sia terminata.</span><span class="sxs-lookup"><span data-stu-id="3766d-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="3766d-107">Inoltre, il proxy crea membri aggiuntivi che contribuiscono a chiamare il metodo in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="3766d-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="3766d-108">Per ogni funzione di servizio Web, *NameOfWebServiceFunction*, il proxy crea una subroutine *NameOfWebServiceFunction*`Async`, un evento *NameOfWebServiceFunction*`Completed` e una classe *NameOfWebServiceFunction*`CompletedEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="3766d-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="3766d-109">L'esempio dimostra come usare i membri asincroni per accedere alla funzione `getTemp` del servizio Web DemoTemperatureService.</span><span class="sxs-lookup"><span data-stu-id="3766d-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>

> [!NOTE]
> <span data-ttu-id="3766d-110">Tale codice non funziona nelle applicazioni Web perché ASP.NET non supporta l'oggetto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="3766d-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>

## <a name="call-a-web-service-asynchronously"></a><span data-ttu-id="3766d-111">Chiamare un servizio Web in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="3766d-111">Call a Web service asynchronously</span></span>

1. <span data-ttu-id="3766d-112">Fare riferimento al servizio Web DemoTemperatureService Web in `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="3766d-112">Reference the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span> <span data-ttu-id="3766d-113">L'indirizzo è</span><span class="sxs-lookup"><span data-stu-id="3766d-113">The address is</span></span>

    ```http
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. <span data-ttu-id="3766d-114">Aggiungere un gestore eventi per l'evento `getTempCompleted`:</span><span class="sxs-lookup"><span data-stu-id="3766d-114">Add an event handler for the `getTempCompleted` event:</span></span>

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > <span data-ttu-id="3766d-115">Non è possibile usare l'istruzione `Handles` per associare un gestore eventi agli eventi dell'oggetto `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="3766d-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>

3. <span data-ttu-id="3766d-116">Aggiungere un campo di cui tenere traccia se il gestore eventi è stato aggiunto all'evento `getTempCompleted`:</span><span class="sxs-lookup"><span data-stu-id="3766d-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. <span data-ttu-id="3766d-117">Aggiungere un metodo che consenta di aggiungere, se necessario, il gestore eventi all'evento `getTempCompleted` e di chiamare il metodo `getTempAsync`:</span><span class="sxs-lookup"><span data-stu-id="3766d-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsync` method:</span></span>

    ```vb
    Sub CallGetTempAsync(ByVal zipCode As Integer)
        If Not handlerAttached Then
            AddHandler My.WebServices.
                TemperatureService.getTempCompleted,
                AddressOf Me.TS_getTempCompleted
            handlerAttached = True
        End If
        My.WebServices.TemperatureService.getTempAsync(zipCode)
    End Sub
    ```

    <span data-ttu-id="3766d-118">Per chiamare il metodo Web `getTemp` in modo asincrono, chiamare il metodo `CallGetTempAsync`.</span><span class="sxs-lookup"><span data-stu-id="3766d-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="3766d-119">Al termine dell'esecuzione del metodo Web il relativo valore restituito viene passato al gestore eventi `getTempCompletedHandler`.</span><span class="sxs-lookup"><span data-stu-id="3766d-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>

## <a name="see-also"></a><span data-ttu-id="3766d-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="3766d-120">See also</span></span>

- [<span data-ttu-id="3766d-121">Accesso ai servizi Web dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3766d-121">Accessing Application Web Services</span></span>](accessing-application-web-services.md)
- [<span data-ttu-id="3766d-122">Oggetto My.WebServices</span><span class="sxs-lookup"><span data-stu-id="3766d-122">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
