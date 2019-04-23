---
title: Cenni preliminari sulla grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a95086645771de61cfc859e34b225992bc16eac9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103935"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="751f6-102">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="751f6-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="751f6-103">è un'application programming interface (API) che costituisce il sottosistema del sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="751f6-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="751f6-104">è responsabile della visualizzazione di informazioni sugli schermi e stampanti.</span><span class="sxs-lookup"><span data-stu-id="751f6-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="751f6-105">Come suggerisce il nome, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è il successore di [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], ovvero le Graphics Device Interface incluse nelle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="751f6-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="751f6-106">Interfaccia di classe gestita</span><span class="sxs-lookup"><span data-stu-id="751f6-106">Managed Class Interface</span></span>  
 <span data-ttu-id="751f6-107">Il [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API viene esposta tramite un set di classi distribuito come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="751f6-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="751f6-108">Questo set di classi viene chiamato il *interfaccia di classe gestita* a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="751f6-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="751f6-109">Di seguito sono elencati gli spazi dei nomi che costituiscono l'interfaccia di classe gestita:</span><span class="sxs-lookup"><span data-stu-id="751f6-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="751f6-110">Con una Graphics Device Interface, ad esempio [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile visualizzare informazioni su un monitor o una stampante senza doversi preoccupare dei dettagli relativi a un dispositivo di visualizzazione particolare.</span><span class="sxs-lookup"><span data-stu-id="751f6-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="751f6-111">Il programmatore effettua chiamate ai metodi forniti dalle classi [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="751f6-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="751f6-112">Tali metodi, a loro volta, effettuano le chiamate appropriate a specifici driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="751f6-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="751f6-113">isola l'applicazione dall'hardware grafico.</span><span class="sxs-lookup"><span data-stu-id="751f6-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="751f6-114">È questo isolamento che consente a un programmatore di creare applicazioni indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="751f6-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751f6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="751f6-115">See also</span></span>

- [<span data-ttu-id="751f6-116">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="751f6-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
