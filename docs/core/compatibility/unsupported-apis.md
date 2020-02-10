---
title: API non supportate in .NET Core
titleSuffix: ''
description: Informazioni sulle API del .NET Framework che generano sempre un'eccezione in .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: c4b94321d30cacd90d5c2ee23c258681683a6faa
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092967"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="0217d-103">API che generano sempre eccezioni in .NET Core</span><span class="sxs-lookup"><span data-stu-id="0217d-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="0217d-104">Le API seguenti genereranno sempre un <xref:System.PlatformNotSupportedException> in .NET Core su tutti o un subset di piattaforme.</span><span class="sxs-lookup"><span data-stu-id="0217d-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="0217d-105">Questo articolo organizza i membri API interessati in base allo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0217d-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0217d-106">Questo articolo è un lavoro in corso.</span><span class="sxs-lookup"><span data-stu-id="0217d-106">This article is a work-in-progress.</span></span> <span data-ttu-id="0217d-107">Non si tratta di un elenco completo di API che generano eccezioni in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0217d-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="0217d-108">Questo articolo non include le implementazioni esplicite dell'interfaccia per la serializzazione binaria generata in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0217d-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="0217d-109">Per altre informazioni, vedere [serializzazione binaria in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="0217d-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="0217d-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="0217d-110">System</span></span>

| <span data-ttu-id="0217d-111">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-111">Member</span></span> | <span data-ttu-id="0217d-112">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-113">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="0217d-114">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="0217d-115">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="0217d-116">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-117">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="0217d-118">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0217d-119">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0217d-120">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-121">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0217d-122">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="0217d-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="0217d-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="0217d-124">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-124">Member</span></span> | <span data-ttu-id="0217d-125">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-126">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-127">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-128">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="0217d-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="0217d-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="0217d-130">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-130">Member</span></span> | <span data-ttu-id="0217d-131">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-132">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-133">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0217d-134">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="0217d-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="0217d-135">System.Configuration</span></span>

| <span data-ttu-id="0217d-136">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-136">Member</span></span> | <span data-ttu-id="0217d-137">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0217d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="0217d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="0217d-139">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="0217d-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="0217d-140">System.Console</span></span>

| <span data-ttu-id="0217d-141">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-141">Member</span></span> | <span data-ttu-id="0217d-142">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="0217d-143">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-143">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-145">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-145">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-147">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-147">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-149">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-149">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="0217d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0217d-151">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-152">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-153">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-154">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-154">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="0217d-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0217d-156">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-156">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-158">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-158">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-160">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-160">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-162">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-162">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-164">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="0217d-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="0217d-165">System.Data.Common</span></span>

| <span data-ttu-id="0217d-166">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-166">Member</span></span> | <span data-ttu-id="0217d-167">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0217d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="0217d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="0217d-169">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="0217d-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="0217d-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="0217d-171">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-171">Member</span></span> | <span data-ttu-id="0217d-172">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0217d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-174">Linux</span><span class="sxs-lookup"><span data-stu-id="0217d-174">Linux</span></span> |
| <span data-ttu-id="0217d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-176">Linux</span><span class="sxs-lookup"><span data-stu-id="0217d-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="0217d-177">macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="0217d-178">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-179">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="0217d-180">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="0217d-181">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="0217d-182">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="0217d-183">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-183">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-185">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-185">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Get)</span><span class="sxs-lookup"><span data-stu-id="0217d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0217d-187">macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-187">macOS</span></span> |
| <span data-ttu-id="0217d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-189">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="0217d-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="0217d-190">System.IO</span></span>

| <span data-ttu-id="0217d-191">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-191">Member</span></span> | <span data-ttu-id="0217d-192">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-193">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-194">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="0217d-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="0217d-195">System.IO.Pipes</span></span>

| <span data-ttu-id="0217d-196">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-196">Member</span></span> | <span data-ttu-id="0217d-197">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="0217d-198">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="0217d-199">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0217d-200">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0217d-201">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-201">Linux and macOS</span></span> |
| <span data-ttu-id="0217d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-203">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="0217d-204">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="0217d-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="0217d-205">System.Media</span></span>

| <span data-ttu-id="0217d-206">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-206">Member</span></span> | <span data-ttu-id="0217d-207">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-208">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="0217d-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="0217d-209">System.Net</span></span>

| <span data-ttu-id="0217d-210">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-210">Member</span></span> | <span data-ttu-id="0217d-211">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0217d-212">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0217d-213">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-214">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-215">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-216">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-217">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-218">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-219">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-220">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-221">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-222">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="0217d-223">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-224">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-225">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-226">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-227">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-228">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="0217d-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="0217d-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="0217d-230">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-230">Member</span></span> | <span data-ttu-id="0217d-231">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="0217d-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="0217d-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="0217d-233">System.Net.Sockets</span></span>

| <span data-ttu-id="0217d-234">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-234">Member</span></span> | <span data-ttu-id="0217d-235">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)?displayProperty=nameWithType> | <span data-ttu-id="0217d-236">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="0217d-237">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="0217d-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="0217d-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="0217d-239">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-239">Member</span></span> | <span data-ttu-id="0217d-240">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="0217d-241">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="0217d-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="0217d-242">System.Reflection</span></span>

| <span data-ttu-id="0217d-243">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-243">Member</span></span> | <span data-ttu-id="0217d-244">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-245">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-246">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-247">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0217d-248">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-249">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-250">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="0217d-251">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="0217d-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="0217d-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="0217d-253">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-253">Member</span></span> | <span data-ttu-id="0217d-254">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="0217d-255">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="0217d-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="0217d-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="0217d-257">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-257">Member</span></span> | <span data-ttu-id="0217d-258">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0217d-259">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="0217d-260">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0217d-261">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0217d-262">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-263">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0217d-264">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0217d-265">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="0217d-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="0217d-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="0217d-267">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-267">Member</span></span> | <span data-ttu-id="0217d-268">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="0217d-269">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="0217d-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="0217d-270">System.Security</span></span>

| <span data-ttu-id="0217d-271">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-271">Member</span></span> | <span data-ttu-id="0217d-272">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="0217d-273">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0217d-274">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-275">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="0217d-276">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0217d-277">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="0217d-278">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="0217d-279">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="0217d-280">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0217d-281">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0217d-282">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="0217d-283">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0217d-284">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="0217d-285">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="0217d-286">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="0217d-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="0217d-287">System.Security.Claims</span></span>

| <span data-ttu-id="0217d-288">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-288">Member</span></span> | <span data-ttu-id="0217d-289">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="0217d-290">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-291">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="0217d-292">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-293">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-294">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="0217d-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="0217d-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="0217d-296">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-296">Member</span></span> | <span data-ttu-id="0217d-297">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-298">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-299">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="0217d-300">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="0217d-301">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="0217d-302">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0217d-303">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="0217d-304">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="0217d-305">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="0217d-306">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="0217d-307">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="0217d-308">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="0217d-309">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="0217d-310">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0217d-311">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0217d-312">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="0217d-313">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-314">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-315">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-316">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-317">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0217d-318">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-319">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-320">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-321">Linux e macOS</span><span class="sxs-lookup"><span data-stu-id="0217d-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-322">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-323">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0217d-324">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0217d-325">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="0217d-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="0217d-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="0217d-327">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-327">Member</span></span> | <span data-ttu-id="0217d-328">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="0217d-329">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0217d-330">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="0217d-331">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="0217d-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="0217d-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="0217d-333">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-333">Member</span></span> | <span data-ttu-id="0217d-334">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-335">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-336">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-337">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-337">All</span></span> |
| <span data-ttu-id="0217d-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo set)</span><span class="sxs-lookup"><span data-stu-id="0217d-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0217d-339">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="0217d-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="0217d-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="0217d-341">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-341">Member</span></span> | <span data-ttu-id="0217d-342">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-343">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="0217d-344">System. Security. Policy</span><span class="sxs-lookup"><span data-stu-id="0217d-344">System.Security.Policy</span></span>

| <span data-ttu-id="0217d-345">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-345">Member</span></span> | <span data-ttu-id="0217d-346">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-347">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="0217d-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="0217d-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="0217d-349">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-349">Member</span></span> | <span data-ttu-id="0217d-350">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-351">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="0217d-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="0217d-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="0217d-353">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-353">Member</span></span> | <span data-ttu-id="0217d-354">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-355">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="0217d-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="0217d-356">System.Threading</span></span>

| <span data-ttu-id="0217d-357">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-357">Member</span></span> | <span data-ttu-id="0217d-358">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-359">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0217d-360">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="0217d-361">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="0217d-362">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="0217d-363">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="0217d-364">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="0217d-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="0217d-365">System.Xml</span></span>

| <span data-ttu-id="0217d-366">Membro</span><span class="sxs-lookup"><span data-stu-id="0217d-366">Member</span></span> | <span data-ttu-id="0217d-367">Piattaforme generate</span><span class="sxs-lookup"><span data-stu-id="0217d-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0217d-368">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0217d-369">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0217d-370">Tutti</span><span class="sxs-lookup"><span data-stu-id="0217d-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="0217d-371">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0217d-371">See also</span></span>

- [<span data-ttu-id="0217d-372">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="0217d-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="0217d-373">Serializzazione binaria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="0217d-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="0217d-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="0217d-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
