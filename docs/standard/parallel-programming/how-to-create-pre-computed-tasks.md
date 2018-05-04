---
title: 'Procedura: Creare attività precalcolate'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ce34e609dc9b1e2a5f1822ce27f65be74a636c86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-pre-computed-tasks"></a>Procedura: Creare attività precalcolate
In questo documento viene descritto come utilizzare il metodo <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> per recuperare i risultati di operazioni di download asincrone contenute in una cache. Tramite il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> viene restituito un oggetto <xref:System.Threading.Tasks.Task%601> finito contenente il valore fornito come relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>. Questo metodo è utile quando si esegue un'operazione asincrona che restituisce un oggetto <xref:System.Threading.Tasks.Task%601> e il risultato di tale oggetto <xref:System.Threading.Tasks.Task%601> è già calcolato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono scaricate stringhe dal Web. Viene definito il metodo `DownloadStringAsync`. Tramite questo metodo vengono scaricate stringhe dal Web in modo asincrono. In questo esempio viene inoltre utilizzato un oggetto <xref:System.Collections.Concurrent.ConcurrentDictionary%602> per memorizzare nella cache i risultati di operazioni precedenti. Se l'indirizzo di input viene mantenuto in questa cache, in `DownloadStringAsync` viene utilizzato il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> per produrre un oggetto <xref:System.Threading.Tasks.Task%601> con il contenuto in corrispondenza dell'indirizzo in questione. In caso contrario, tramite `DownloadStringAsync` viene scaricato il file dal Web e viene aggiunto il risultato alla cache.  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 In questo esempio viene calcolato il tempo necessario per scaricare più stringhe due volte. Per il secondo set di operazioni di download deve essere impiegato meno tempo del primo poiché i risultati sono contenuti nella cache. Il metodo <xref:System.Threading.Tasks.Task.FromResult%2A> consente al metodo `DownloadStringAsync` di creare oggetti di <xref:System.Threading.Tasks.Task%601> contenenti questi risultati precalcolati.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Copiare il codice di esempio e incollarlo in un progetto di Visual Studio oppure incollarlo in un file denominato `CachedDownloads.cs` (`CachedDownloads.vb` per Visual Basic) e quindi eseguire il comando riportato di seguito in una finestra del prompt dei comandi di Visual Studio.  
  
 Visual C#  
  
 **csc.exe CachedDownloads.cs**  
  
 Visual Basic  
  
 **vbc.exe CachedDownloads.vb**  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
