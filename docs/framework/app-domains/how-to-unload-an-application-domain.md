---
title: "Procedura: Scaricare un dominio dell'applicazione"
description: Leggere come scaricare un dominio applicazione in .NET, usando il metodo AppDomain. Unload per arrestare normalmente il dominio applicazione specificato.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
ms.openlocfilehash: b64a9553f63aa4a8deb57f23a97fa464edd64fee
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104661"
---
# <a name="how-to-unload-an-application-domain"></a>Procedura: Scaricare un dominio dell'applicazione
Dopo aver usato un dominio dell'applicazione, scaricare il dominio usando il metodo <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>. Il metodo **Unload** consente di chiudere normalmente il dominio dell'applicazione specificato. Durante il processo di scaricamento, nessun nuovo thread può accedere al dominio dell'applicazione e tutte le strutture dei dati specifiche del dominio dell'applicazione vengono liberate.  
  
 Gli assembly caricati nel dominio dell'applicazione vengono rimossi e non risultano più disponibili. Se un assembly nel dominio dell'applicazione è indipendente dal dominio, i dati relativi all'assembly rimarranno in memoria fino alla chiusura dell'intero processo. L'unico meccanismo che consente lo scaricamento di un assembly indipendente dal dominio consiste nella chiusura dell'intero processo. In alcune situazioni non è possibile scaricare un dominio dell'applicazione e viene generata un'eccezione <xref:System.CannotUnloadAppDomainException>.  
  
 L'esempio seguente consente di creare un nuovo dominio dell'applicazione denominato `MyDomain`, stampare alcune informazioni nella console e quindi scaricare il dominio dell'applicazione. Si noti che il codice tenta in seguito di stampare il nome descrittivo del dominio dell'applicazione scaricato nella console. Questa operazione genera un'eccezione che viene gestita da istruzioni try/catch alla fine del programma.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione con i domini dell'applicazione](application-domains.md#programming-with-application-domains)
- [Procedura: Creare un dominio dell'applicazione](how-to-create-an-application-domain.md)
- [Uso dei domini dell'applicazione](use.md)
