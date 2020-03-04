---
title: 'Procedura: caricare e scaricare assembly'
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: a520ffd41c3465737be7494d374cbcf64e3f1b85
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155776"
---
# <a name="how-to-load-and-unload-assemblies"></a>Procedura: caricare e scaricare assembly
Gli assembly a cui fa riferimento il programma verranno caricati automaticamente dal Common Language Runtime, ma è anche possibile caricare in modo dinamico assembly specifici nel dominio applicazione corrente. Per altre informazioni, vedere [procedura: caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).

In .NET Framework non esiste alcun modo per scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono. Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini dell'applicazione che lo contengono. In .NET Core, la classe <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> gestisce lo scaricamento degli assembly. Per altre informazioni, vedere [come usare ed eseguire il debug dello scaricamento di assembly in .NET Core](unloadability.md).

## <a name="load-and-unload-assemblies"></a>Caricare e scaricare gli assembly

Per caricare un assembly in un dominio applicazione, usare uno dei diversi metodi di caricamento contenuti nelle classi <xref:System.AppDomain> e <xref:System.Reflection.Assembly>. Per altre informazioni, vedere [procedura: caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md). Si noti che .NET Core supporta solo un singolo dominio applicazione.

Per scaricare un assembly nella .NET Framework, è necessario scaricare tutti i domini applicazione che lo contengono. Per scaricare un dominio applicazione, usare il metodo <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [procedura: scaricare un dominio dell'applicazione](../../framework/app-domains/how-to-unload-an-application-domain.md).

Se si desidera scaricare alcuni assembly ma non altri in un'applicazione .NET Framework, è consigliabile creare un nuovo dominio applicazione, eseguire il codice all'interno del dominio e quindi scaricare tale dominio applicazione. Per altre informazioni, vedere [procedura: scaricare un dominio dell'applicazione](../../framework/app-domains/how-to-unload-an-application-domain.md).  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assembly in .NET](index.md)
- [Procedura: caricare assembly in un dominio applicazione](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
