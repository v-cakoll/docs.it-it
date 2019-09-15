---
title: 'Procedura: Caricare e scaricare gli assembly'
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: 77ea97c2fc324287e9c697d630def98241432c9f
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973201"
---
# <a name="how-to-load-and-unload-assemblies"></a>Procedura: Caricare e scaricare gli assembly
Gli assembly a cui fa riferimento il programma verranno caricati automaticamente dal Common Language Runtime, ma è anche possibile caricare in modo dinamico assembly specifici nel dominio applicazione corrente. Per altre informazioni, vedere [Procedura: Caricare gli assembly in un dominio](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)applicazione.

In .NET Framework non esiste alcun modo per scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono. Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono. In .NET Core la <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> classe gestisce lo scaricamento degli assembly. Per altre informazioni, vedere [come usare ed eseguire il debug dello scaricamento di assembly in .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Caricare e scaricare gli assembly

Per caricare un assembly in un dominio applicazione, usare uno dei diversi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e. <xref:System.Reflection.Assembly> Per altre informazioni, vedere [Procedura: Caricare gli assembly in un dominio](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)applicazione. Si noti che .NET Core supporta solo un singolo dominio applicazione. 

Per scaricare un assembly nella .NET Framework, è necessario scaricare tutti i domini applicazione che lo contengono. Per scaricare un dominio applicazione, utilizzare il <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> metodo. Per altre informazioni, vedere [Procedura: Scarica un dominio](../../framework/app-domains/how-to-unload-an-application-domain.md)applicazione.

Se si desidera scaricare alcuni assembly ma non altri in un'applicazione .NET Framework, è consigliabile creare un nuovo dominio applicazione, eseguire il codice all'interno del dominio e quindi scaricare tale dominio applicazione. Per altre informazioni, vedere [Procedura: Scarica un dominio](../../framework/app-domains/how-to-unload-an-application-domain.md)applicazione.  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)
- [Procedura: Caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
