---
title: Scrittura di progetti destinati a .NET Framework 3.0 e 3.5 in Visual Studio 2010
ms.date: 03/30/2017
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
ms.openlocfilehash: 1469ce2906c1101bae4098cbcabd4a10a64c1c7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513827"
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a>Scrittura di progetti destinati a .NET Framework 3.0 e 3.5 in Visual Studio 2010
È possibile usare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] per creare progetti destinati a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versione 3.0 o 3.5. In questo argomento viene descritto come eseguire questa operazione.  
  
> [!NOTE]
>  Quando si aggiungono attività, verificare che venga impostata la versione desiderata di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Se si modifica la versione di destinazione del flusso di lavoro dopo l'aggiunta delle attività, non sarà possibile convalidare il flusso di lavoro.  
  
> [!WARNING]
>  L'apertura di flussi di lavoro esistenti in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] in cui sono presenti attività di .NET Framework 3.5 provocherà un errore in `this.SetValue()`. Per aprire progetti creati con versioni precedenti di .NET Framework, aprire prima un flusso di lavoro vuoto nella finestra di progettazione, quindi aggiungere un'attività .NET Framework 3.5.  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a>Per creare un progetto .NET Framework 3.0 o 3.5 in Visual Studio 2010  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Selezionare **File**, **nuova**, **progetto**.  
  
3.  Nell'elenco a discesa nella parte superiore della finestra di dialogo selezionare la versione desiderata di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a>Per aggiornare la versione di destinazione di .NET Framework  
  
1.  Fare clic sul progetto in Esplora soluzioni e selezionare **proprietà**.  
  
2.  Nel **Framework di destinazione** elenco a discesa, selezionare la versione desiderata.
