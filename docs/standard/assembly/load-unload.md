---
title: 'Procedura: caricare e scaricare assemblyHow to: Load and unload assemblies'
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: a520ffd41c3465737be7494d374cbcf64e3f1b85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155776"
---
# <a name="how-to-load-and-unload-assemblies"></a>Procedura: caricare e scaricare assemblyHow to: Load and unload assemblies
Gli assembly a cui fa riferimento il programma verranno caricati automaticamente da Common Language Runtime, ma è anche possibile caricare in modo dinamico assembly specifici nel dominio applicazione corrente. Per ulteriori informazioni, vedere [Procedura: caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

In .NET Framework non è possibile scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono. Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono. In .NET Core <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> la classe gestisce lo scaricamento degli assembly. Per ulteriori informazioni, vedere Come utilizzare ed eseguire il debug di [unloadability degli assembly in .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Caricare e scaricare gli assembly

Per caricare un assembly in un dominio applicazione, utilizzare uno <xref:System.AppDomain> <xref:System.Reflection.Assembly>dei diversi metodi di caricamento contenuti nelle classi e . Per ulteriori informazioni, vedere [Procedura: caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Si noti che .NET Core supporta solo un singolo dominio applicazione.

Per scaricare un assembly in .NET Framework, è necessario scaricare tutti i domini applicazione che lo contengono. Per scaricare un dominio applicazione, utilizzare il <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metodo . Per ulteriori informazioni, vedere [Procedura: scaricare un dominio applicazione](../../framework/app-domains/how-to-unload-an-application-domain.md).

Se si desidera scaricare alcuni assembly ma non altri in un'applicazione .NET Framework, è consigliabile creare un nuovo dominio applicazione, eseguire il codice all'interno di tale dominio e quindi scaricare tale dominio applicazione. Per ulteriori informazioni, vedere [Procedura: scaricare un dominio applicazione](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)
- [Procedura: caricare assembly in un dominio applicazioneHow to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
