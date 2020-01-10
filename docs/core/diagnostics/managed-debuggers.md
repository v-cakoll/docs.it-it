---
title: Debugger gestiti-.NET Core
description: Panoramica dei debugger gestiti di Visual Studio e Visual Studio Code.
ms.date: 08/05/2019
ms.openlocfilehash: 065b1b0fc32eb76b398cb3821c8592a1955c9359
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715560"
---
# <a name="net-core-managed-debuggers"></a><span data-ttu-id="2966b-103">Debugger gestiti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="2966b-103">.NET Core managed debuggers</span></span>

<span data-ttu-id="2966b-104">I debugger consentono di sospendere o eseguire i programmi in modo dettagliato.</span><span class="sxs-lookup"><span data-stu-id="2966b-104">Debuggers allow programs to be paused or executed step-by-step.</span></span> <span data-ttu-id="2966b-105">Una volta sospesa, è possibile visualizzare lo stato corrente del processo.</span><span class="sxs-lookup"><span data-stu-id="2966b-105">When paused, the current state of the process can be viewed.</span></span> <span data-ttu-id="2966b-106">Esaminando le sezioni chiave, si ottiene la comprensione del codice e il motivo per cui produce il risultato.</span><span class="sxs-lookup"><span data-stu-id="2966b-106">By stepping through key sections, you gain understanding of your code and why it produces the result that it does.</span></span>

<span data-ttu-id="2966b-107">Microsoft fornisce i debugger per il codice gestito in **Visual Studio** e **Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="2966b-107">Microsoft provides debuggers for managed code in **Visual Studio** and **Visual Studio Code**.</span></span>

## <a name="visual-studio-managed-debugger"></a><span data-ttu-id="2966b-108">Debugger gestito di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2966b-108">Visual Studio managed debugger</span></span>

<span data-ttu-id="2966b-109">**Visual Studio** è un Integrated Development Environment con il debugger più completo disponibile.</span><span class="sxs-lookup"><span data-stu-id="2966b-109">**Visual Studio** is an integrated development environment with the most comprehensive debugger available.</span></span> <span data-ttu-id="2966b-110">Visual Studio è un'ottima scelta per gli sviluppatori che lavorano su Windows.</span><span class="sxs-lookup"><span data-stu-id="2966b-110">Visual Studio is an excellent choice for developers working on Windows.</span></span>

- [<span data-ttu-id="2966b-111">Esercitazione: debug di un'applicazione .NET Core in Windows con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2966b-111">Tutorial - Debugging a .NET Core application on Windows with Visual Studio</span></span>](../tutorials/debugging-with-visual-studio.md)

<span data-ttu-id="2966b-112">Mentre Visual Studio è un'applicazione Windows, può comunque essere usato per eseguire il debug remoto di app Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="2966b-112">While Visual Studio is a Windows application, it can still be used to debug Linux and macOS apps remotely.</span></span>

- [<span data-ttu-id="2966b-113">Debug di un'applicazione .NET Core in Linux/OSX con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2966b-113">Debugging a .NET Core application on Linux/OSX with Visual Studio</span></span>](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 <span data-ttu-id="2966b-114">Il debug di ASP.NET Core app richiede istruzioni leggermente diverse.</span><span class="sxs-lookup"><span data-stu-id="2966b-114">Debugging ASP.NET Core apps require slightly different instructions.</span></span>

- [<span data-ttu-id="2966b-115">Eseguire il debug di app ASP.NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2966b-115">Debug ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a><span data-ttu-id="2966b-116">Debugger gestito di Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2966b-116">Visual Studio Code managed debugger</span></span>

<span data-ttu-id="2966b-117">**Visual Studio Code** è un editor di codice multipiattaforma leggero.</span><span class="sxs-lookup"><span data-stu-id="2966b-117">**Visual Studio Code** is a lightweight cross-platform code editor.</span></span> <span data-ttu-id="2966b-118">Usa la stessa implementazione del debugger .NET Core di Visual Studio, ma con un'interfaccia utente semplificata.</span><span class="sxs-lookup"><span data-stu-id="2966b-118">It uses the same .NET Core debugger implementation as Visual Studio, but with a simplified user interface.</span></span>

- [<span data-ttu-id="2966b-119">Esercitazione: debug di un'applicazione .NET Core con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2966b-119">Tutorial - Debugging a .NET Core application with Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md#debug)
- <span data-ttu-id="2966b-120">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging) (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="2966b-120">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)</span></span>
