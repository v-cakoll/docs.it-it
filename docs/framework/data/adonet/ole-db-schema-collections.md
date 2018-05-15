---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="28323-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="28323-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="28323-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="28323-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="28323-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="28323-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="28323-105">Il Driver OLE DB Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="28323-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="28323-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-106">Tables</span></span>  
  
-   <span data-ttu-id="28323-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-107">Columns</span></span>  
  
-   <span data-ttu-id="28323-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-108">Procedures</span></span>  
  
-   <span data-ttu-id="28323-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="28323-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="28323-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="28323-110">Catalog</span></span>  
  
-   <span data-ttu-id="28323-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="28323-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-112">Tables</span></span>  
  
|<span data-ttu-id="28323-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-113">ColumnName</span></span>|<span data-ttu-id="28323-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-115">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-116">String</span><span class="sxs-lookup"><span data-stu-id="28323-116">String</span></span>|  
|<span data-ttu-id="28323-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-118">String</span><span class="sxs-lookup"><span data-stu-id="28323-118">String</span></span>|  
|<span data-ttu-id="28323-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-119">TABLE_NAME</span></span>|<span data-ttu-id="28323-120">String</span><span class="sxs-lookup"><span data-stu-id="28323-120">String</span></span>|  
|<span data-ttu-id="28323-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-121">TABLE_TYPE</span></span>|<span data-ttu-id="28323-122">String</span><span class="sxs-lookup"><span data-stu-id="28323-122">String</span></span>|  
|<span data-ttu-id="28323-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-123">TABLE_GUID</span></span>|<span data-ttu-id="28323-124">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-124">Guid</span></span>|  
|<span data-ttu-id="28323-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-125">DESCRIPTION</span></span>|<span data-ttu-id="28323-126">String</span><span class="sxs-lookup"><span data-stu-id="28323-126">String</span></span>|  
|<span data-ttu-id="28323-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-127">TABLE_PROPID</span></span>|<span data-ttu-id="28323-128">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-128">Int64</span></span>|  
|<span data-ttu-id="28323-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-129">DATE_CREATED</span></span>|<span data-ttu-id="28323-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-130">DateTime</span></span>|  
|<span data-ttu-id="28323-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-131">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="28323-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-133">Columns</span></span>  
  
|<span data-ttu-id="28323-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-134">ColumnName</span></span>|<span data-ttu-id="28323-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-136">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-137">String</span><span class="sxs-lookup"><span data-stu-id="28323-137">String</span></span>|  
|<span data-ttu-id="28323-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-139">String</span><span class="sxs-lookup"><span data-stu-id="28323-139">String</span></span>|  
|<span data-ttu-id="28323-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-140">TABLE_NAME</span></span>|<span data-ttu-id="28323-141">String</span><span class="sxs-lookup"><span data-stu-id="28323-141">String</span></span>|  
|<span data-ttu-id="28323-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-142">COLUMN_NAME</span></span>|<span data-ttu-id="28323-143">String</span><span class="sxs-lookup"><span data-stu-id="28323-143">String</span></span>|  
|<span data-ttu-id="28323-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-144">COLUMN_GUID</span></span>|<span data-ttu-id="28323-145">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-145">Guid</span></span>|  
|<span data-ttu-id="28323-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-146">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-147">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-147">Int64</span></span>|  
|<span data-ttu-id="28323-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-149">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-149">Int64</span></span>|  
|<span data-ttu-id="28323-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="28323-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-151">Boolean</span></span>|  
|<span data-ttu-id="28323-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="28323-153">String</span><span class="sxs-lookup"><span data-stu-id="28323-153">String</span></span>|  
|<span data-ttu-id="28323-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="28323-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="28323-155">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-155">Int64</span></span>|  
|<span data-ttu-id="28323-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="28323-156">IS_NULLABLE</span></span>|<span data-ttu-id="28323-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-157">Boolean</span></span>|  
|<span data-ttu-id="28323-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-158">DATA_TYPE</span></span>|<span data-ttu-id="28323-159">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-159">Int32</span></span>|  
|<span data-ttu-id="28323-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-160">TYPE_GUID</span></span>|<span data-ttu-id="28323-161">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-161">Guid</span></span>|  
|<span data-ttu-id="28323-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="28323-163">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-163">Int64</span></span>|  
|<span data-ttu-id="28323-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="28323-165">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-165">Int64</span></span>|  
|<span data-ttu-id="28323-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="28323-167">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-167">Int32</span></span>|  
|<span data-ttu-id="28323-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="28323-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="28323-169">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-169">Int16</span></span>|  
|<span data-ttu-id="28323-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="28323-171">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-171">Int64</span></span>|  
|<span data-ttu-id="28323-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="28323-173">String</span><span class="sxs-lookup"><span data-stu-id="28323-173">String</span></span>|  
|<span data-ttu-id="28323-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="28323-175">String</span><span class="sxs-lookup"><span data-stu-id="28323-175">String</span></span>|  
|<span data-ttu-id="28323-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="28323-177">String</span><span class="sxs-lookup"><span data-stu-id="28323-177">String</span></span>|  
|<span data-ttu-id="28323-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="28323-179">String</span><span class="sxs-lookup"><span data-stu-id="28323-179">String</span></span>|  
|<span data-ttu-id="28323-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="28323-181">String</span><span class="sxs-lookup"><span data-stu-id="28323-181">String</span></span>|  
|<span data-ttu-id="28323-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-182">COLLATION_NAME</span></span>|<span data-ttu-id="28323-183">String</span><span class="sxs-lookup"><span data-stu-id="28323-183">String</span></span>|  
|<span data-ttu-id="28323-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="28323-185">String</span><span class="sxs-lookup"><span data-stu-id="28323-185">String</span></span>|  
|<span data-ttu-id="28323-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="28323-187">String</span><span class="sxs-lookup"><span data-stu-id="28323-187">String</span></span>|  
|<span data-ttu-id="28323-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-188">DOMAIN_NAME</span></span>|<span data-ttu-id="28323-189">String</span><span class="sxs-lookup"><span data-stu-id="28323-189">String</span></span>|  
|<span data-ttu-id="28323-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-190">DESCRIPTION</span></span>|<span data-ttu-id="28323-191">String</span><span class="sxs-lookup"><span data-stu-id="28323-191">String</span></span>|  
|<span data-ttu-id="28323-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="28323-192">COLUMN_LCID</span></span>|<span data-ttu-id="28323-193">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-193">Int32</span></span>|  
|<span data-ttu-id="28323-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="28323-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="28323-195">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-195">Int32</span></span>|  
|<span data-ttu-id="28323-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="28323-196">COLUMN_SORTID</span></span>|<span data-ttu-id="28323-197">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-197">Int32</span></span>|  
|<span data-ttu-id="28323-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="28323-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="28323-199">Byte[]</span></span>|  
|<span data-ttu-id="28323-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="28323-200">IS_COMPUTED</span></span>|<span data-ttu-id="28323-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="28323-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-202">Procedures</span></span>  
  
|<span data-ttu-id="28323-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-203">ColumnName</span></span>|<span data-ttu-id="28323-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="28323-206">String</span><span class="sxs-lookup"><span data-stu-id="28323-206">String</span></span>|  
|<span data-ttu-id="28323-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="28323-208">String</span><span class="sxs-lookup"><span data-stu-id="28323-208">String</span></span>|  
|<span data-ttu-id="28323-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="28323-210">String</span><span class="sxs-lookup"><span data-stu-id="28323-210">String</span></span>|  
|<span data-ttu-id="28323-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="28323-212">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-212">Int16</span></span>|  
|<span data-ttu-id="28323-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="28323-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="28323-214">String</span><span class="sxs-lookup"><span data-stu-id="28323-214">String</span></span>|  
|<span data-ttu-id="28323-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-215">DESCRIPTION</span></span>|<span data-ttu-id="28323-216">String</span><span class="sxs-lookup"><span data-stu-id="28323-216">String</span></span>|  
|<span data-ttu-id="28323-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-217">DATE_CREATED</span></span>|<span data-ttu-id="28323-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-218">DateTime</span></span>|  
|<span data-ttu-id="28323-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-219">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="28323-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="28323-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="28323-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-222">ColumnName</span></span>|<span data-ttu-id="28323-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="28323-225">String</span><span class="sxs-lookup"><span data-stu-id="28323-225">String</span></span>|  
|<span data-ttu-id="28323-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="28323-227">String</span><span class="sxs-lookup"><span data-stu-id="28323-227">String</span></span>|  
|<span data-ttu-id="28323-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="28323-229">String</span><span class="sxs-lookup"><span data-stu-id="28323-229">String</span></span>|  
|<span data-ttu-id="28323-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-230">PARAMETER_NAME</span></span>|<span data-ttu-id="28323-231">String</span><span class="sxs-lookup"><span data-stu-id="28323-231">String</span></span>|  
|<span data-ttu-id="28323-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-233">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-233">Int32</span></span>|  
|<span data-ttu-id="28323-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="28323-235">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-235">Int32</span></span>|  
|<span data-ttu-id="28323-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="28323-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-237">Boolean</span></span>|  
|<span data-ttu-id="28323-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="28323-239">String</span><span class="sxs-lookup"><span data-stu-id="28323-239">String</span></span>|  
|<span data-ttu-id="28323-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="28323-240">IS_NULLABLE</span></span>|<span data-ttu-id="28323-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-241">Boolean</span></span>|  
|<span data-ttu-id="28323-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-242">DATA_TYPE</span></span>|<span data-ttu-id="28323-243">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-243">Int32</span></span>|  
|<span data-ttu-id="28323-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="28323-245">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-245">Int64</span></span>|  
|<span data-ttu-id="28323-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="28323-247">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-247">Int64</span></span>|  
|<span data-ttu-id="28323-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="28323-249">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-249">Int32</span></span>|  
|<span data-ttu-id="28323-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="28323-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="28323-251">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-251">Int16</span></span>|  
|<span data-ttu-id="28323-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-252">DESCRIPTION</span></span>|<span data-ttu-id="28323-253">String</span><span class="sxs-lookup"><span data-stu-id="28323-253">String</span></span>|  
|<span data-ttu-id="28323-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-254">TYPE_NAME</span></span>|<span data-ttu-id="28323-255">String</span><span class="sxs-lookup"><span data-stu-id="28323-255">String</span></span>|  
|<span data-ttu-id="28323-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="28323-257">String</span><span class="sxs-lookup"><span data-stu-id="28323-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="28323-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="28323-258">Catalog</span></span>  
  
|<span data-ttu-id="28323-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-259">ColumnName</span></span>|<span data-ttu-id="28323-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-261">CATALOG_NAME</span></span>|<span data-ttu-id="28323-262">String</span><span class="sxs-lookup"><span data-stu-id="28323-262">String</span></span>|  
|<span data-ttu-id="28323-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-263">DESCRIPTION</span></span>|<span data-ttu-id="28323-264">String</span><span class="sxs-lookup"><span data-stu-id="28323-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="28323-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-265">Indexes</span></span>  
  
|<span data-ttu-id="28323-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-266">ColumnName</span></span>|<span data-ttu-id="28323-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-268">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-269">String</span><span class="sxs-lookup"><span data-stu-id="28323-269">String</span></span>|  
|<span data-ttu-id="28323-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-271">String</span><span class="sxs-lookup"><span data-stu-id="28323-271">String</span></span>|  
|<span data-ttu-id="28323-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-272">TABLE_NAME</span></span>|<span data-ttu-id="28323-273">String</span><span class="sxs-lookup"><span data-stu-id="28323-273">String</span></span>|  
|<span data-ttu-id="28323-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-274">INDEX_CATALOG</span></span>|<span data-ttu-id="28323-275">String</span><span class="sxs-lookup"><span data-stu-id="28323-275">String</span></span>|  
|<span data-ttu-id="28323-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="28323-277">String</span><span class="sxs-lookup"><span data-stu-id="28323-277">String</span></span>|  
|<span data-ttu-id="28323-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-278">INDEX_NAME</span></span>|<span data-ttu-id="28323-279">String</span><span class="sxs-lookup"><span data-stu-id="28323-279">String</span></span>|  
|<span data-ttu-id="28323-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="28323-280">PRIMARY_KEY</span></span>|<span data-ttu-id="28323-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-281">Boolean</span></span>|  
|<span data-ttu-id="28323-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="28323-282">UNIQUE</span></span>|<span data-ttu-id="28323-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-283">Boolean</span></span>|  
|<span data-ttu-id="28323-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="28323-284">CLUSTERED</span></span>|<span data-ttu-id="28323-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-285">Boolean</span></span>|  
|<span data-ttu-id="28323-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-286">TYPE</span></span>|<span data-ttu-id="28323-287">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-287">Int32</span></span>|  
|<span data-ttu-id="28323-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="28323-288">FILL_FACTOR</span></span>|<span data-ttu-id="28323-289">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-289">Int32</span></span>|  
|<span data-ttu-id="28323-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="28323-290">INITIAL_SIZE</span></span>|<span data-ttu-id="28323-291">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-291">Int32</span></span>|  
|<span data-ttu-id="28323-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="28323-292">NULLS</span></span>|<span data-ttu-id="28323-293">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-293">Int32</span></span>|  
|<span data-ttu-id="28323-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="28323-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="28323-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-295">Boolean</span></span>|  
|<span data-ttu-id="28323-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="28323-296">AUTO_UPDATE</span></span>|<span data-ttu-id="28323-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-297">Boolean</span></span>|  
|<span data-ttu-id="28323-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-298">NULL_COLLATION</span></span>|<span data-ttu-id="28323-299">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-299">Int32</span></span>|  
|<span data-ttu-id="28323-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-301">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-301">Int64</span></span>|  
|<span data-ttu-id="28323-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-302">COLUMN_NAME</span></span>|<span data-ttu-id="28323-303">String</span><span class="sxs-lookup"><span data-stu-id="28323-303">String</span></span>|  
|<span data-ttu-id="28323-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-304">COLUMN_GUID</span></span>|<span data-ttu-id="28323-305">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-305">Guid</span></span>|  
|<span data-ttu-id="28323-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-306">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-307">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-307">Int64</span></span>|  
|<span data-ttu-id="28323-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-308">COLLATION</span></span>|<span data-ttu-id="28323-309">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-309">Int16</span></span>|  
|<span data-ttu-id="28323-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="28323-310">CARDINALITY</span></span>|<span data-ttu-id="28323-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="28323-311">Decimal</span></span>|  
|<span data-ttu-id="28323-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="28323-312">PAGES</span></span>|<span data-ttu-id="28323-313">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-313">Int32</span></span>|  
|<span data-ttu-id="28323-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="28323-314">FILTER_CONDITION</span></span>|<span data-ttu-id="28323-315">String</span><span class="sxs-lookup"><span data-stu-id="28323-315">String</span></span>|  
|<span data-ttu-id="28323-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="28323-316">INTEGRATED</span></span>|<span data-ttu-id="28323-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="28323-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="28323-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="28323-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="28323-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="28323-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-320">Tables</span></span>  
  
-   <span data-ttu-id="28323-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-321">Columns</span></span>  
  
-   <span data-ttu-id="28323-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-322">Procedures</span></span>  
  
-   <span data-ttu-id="28323-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="28323-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="28323-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="28323-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="28323-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="28323-325">Views</span></span>  
  
-   <span data-ttu-id="28323-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="28323-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-327">Tables</span></span>  
  
|<span data-ttu-id="28323-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-328">ColumnName</span></span>|<span data-ttu-id="28323-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-330">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-331">String</span><span class="sxs-lookup"><span data-stu-id="28323-331">String</span></span>|  
|<span data-ttu-id="28323-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-333">String</span><span class="sxs-lookup"><span data-stu-id="28323-333">String</span></span>|  
|<span data-ttu-id="28323-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-334">TABLE_NAME</span></span>|<span data-ttu-id="28323-335">String</span><span class="sxs-lookup"><span data-stu-id="28323-335">String</span></span>|  
|<span data-ttu-id="28323-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-336">TABLE_TYPE</span></span>|<span data-ttu-id="28323-337">String</span><span class="sxs-lookup"><span data-stu-id="28323-337">String</span></span>|  
|<span data-ttu-id="28323-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-338">TABLE_GUID</span></span>|<span data-ttu-id="28323-339">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-339">Guid</span></span>|  
|<span data-ttu-id="28323-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-340">DESCRIPTION</span></span>|<span data-ttu-id="28323-341">String</span><span class="sxs-lookup"><span data-stu-id="28323-341">String</span></span>|  
|<span data-ttu-id="28323-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-342">TABLE_PROPID</span></span>|<span data-ttu-id="28323-343">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-343">Int64</span></span>|  
|<span data-ttu-id="28323-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-344">DATE_CREATED</span></span>|<span data-ttu-id="28323-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-345">DateTime</span></span>|  
|<span data-ttu-id="28323-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-346">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="28323-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-348">Columns</span></span>  
  
|<span data-ttu-id="28323-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-349">ColumnName</span></span>|<span data-ttu-id="28323-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-351">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-352">String</span><span class="sxs-lookup"><span data-stu-id="28323-352">String</span></span>|  
|<span data-ttu-id="28323-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-354">String</span><span class="sxs-lookup"><span data-stu-id="28323-354">String</span></span>|  
|<span data-ttu-id="28323-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-355">TABLE_NAME</span></span>|<span data-ttu-id="28323-356">String</span><span class="sxs-lookup"><span data-stu-id="28323-356">String</span></span>|  
|<span data-ttu-id="28323-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-357">COLUMN_NAME</span></span>|<span data-ttu-id="28323-358">String</span><span class="sxs-lookup"><span data-stu-id="28323-358">String</span></span>|  
|<span data-ttu-id="28323-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-359">COLUMN_GUID</span></span>|<span data-ttu-id="28323-360">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-360">Guid</span></span>|  
|<span data-ttu-id="28323-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-361">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-362">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-362">Int64</span></span>|  
|<span data-ttu-id="28323-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-364">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-364">Int64</span></span>|  
|<span data-ttu-id="28323-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="28323-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-366">Boolean</span></span>|  
|<span data-ttu-id="28323-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="28323-368">String</span><span class="sxs-lookup"><span data-stu-id="28323-368">String</span></span>|  
|<span data-ttu-id="28323-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="28323-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="28323-370">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-370">Int64</span></span>|  
|<span data-ttu-id="28323-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="28323-371">IS_NULLABLE</span></span>|<span data-ttu-id="28323-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-372">Boolean</span></span>|  
|<span data-ttu-id="28323-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-373">DATA_TYPE</span></span>|<span data-ttu-id="28323-374">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-374">Int32</span></span>|  
|<span data-ttu-id="28323-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-375">TYPE_GUID</span></span>|<span data-ttu-id="28323-376">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-376">Guid</span></span>|  
|<span data-ttu-id="28323-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="28323-378">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-378">Int64</span></span>|  
|<span data-ttu-id="28323-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="28323-380">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-380">Int64</span></span>|  
|<span data-ttu-id="28323-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="28323-382">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-382">Int32</span></span>|  
|<span data-ttu-id="28323-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="28323-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="28323-384">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-384">Int16</span></span>|  
|<span data-ttu-id="28323-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="28323-386">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-386">Int64</span></span>|  
|<span data-ttu-id="28323-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="28323-388">String</span><span class="sxs-lookup"><span data-stu-id="28323-388">String</span></span>|  
|<span data-ttu-id="28323-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="28323-390">String</span><span class="sxs-lookup"><span data-stu-id="28323-390">String</span></span>|  
|<span data-ttu-id="28323-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="28323-392">String</span><span class="sxs-lookup"><span data-stu-id="28323-392">String</span></span>|  
|<span data-ttu-id="28323-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="28323-394">String</span><span class="sxs-lookup"><span data-stu-id="28323-394">String</span></span>|  
|<span data-ttu-id="28323-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="28323-396">String</span><span class="sxs-lookup"><span data-stu-id="28323-396">String</span></span>|  
|<span data-ttu-id="28323-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-397">COLLATION_NAME</span></span>|<span data-ttu-id="28323-398">String</span><span class="sxs-lookup"><span data-stu-id="28323-398">String</span></span>|  
|<span data-ttu-id="28323-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="28323-400">String</span><span class="sxs-lookup"><span data-stu-id="28323-400">String</span></span>|  
|<span data-ttu-id="28323-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="28323-402">String</span><span class="sxs-lookup"><span data-stu-id="28323-402">String</span></span>|  
|<span data-ttu-id="28323-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-403">DOMAIN_NAME</span></span>|<span data-ttu-id="28323-404">String</span><span class="sxs-lookup"><span data-stu-id="28323-404">String</span></span>|  
|<span data-ttu-id="28323-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-405">DESCRIPTION</span></span>|<span data-ttu-id="28323-406">String</span><span class="sxs-lookup"><span data-stu-id="28323-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="28323-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-407">Procedures</span></span>  
  
|<span data-ttu-id="28323-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-408">ColumnName</span></span>|<span data-ttu-id="28323-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="28323-411">String</span><span class="sxs-lookup"><span data-stu-id="28323-411">String</span></span>|  
|<span data-ttu-id="28323-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="28323-413">String</span><span class="sxs-lookup"><span data-stu-id="28323-413">String</span></span>|  
|<span data-ttu-id="28323-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="28323-415">String</span><span class="sxs-lookup"><span data-stu-id="28323-415">String</span></span>|  
|<span data-ttu-id="28323-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="28323-417">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-417">Int16</span></span>|  
|<span data-ttu-id="28323-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="28323-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="28323-419">String</span><span class="sxs-lookup"><span data-stu-id="28323-419">String</span></span>|  
|<span data-ttu-id="28323-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-420">DESCRIPTION</span></span>|<span data-ttu-id="28323-421">String</span><span class="sxs-lookup"><span data-stu-id="28323-421">String</span></span>|  
|<span data-ttu-id="28323-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-422">DATE_CREATED</span></span>|<span data-ttu-id="28323-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-423">DateTime</span></span>|  
|<span data-ttu-id="28323-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-424">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="28323-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="28323-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="28323-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-427">ColumnName</span></span>|<span data-ttu-id="28323-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="28323-430">String</span><span class="sxs-lookup"><span data-stu-id="28323-430">String</span></span>|  
|<span data-ttu-id="28323-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="28323-432">String</span><span class="sxs-lookup"><span data-stu-id="28323-432">String</span></span>|  
|<span data-ttu-id="28323-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="28323-434">String</span><span class="sxs-lookup"><span data-stu-id="28323-434">String</span></span>|  
|<span data-ttu-id="28323-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-435">COLUMN_NAME</span></span>|<span data-ttu-id="28323-436">String</span><span class="sxs-lookup"><span data-stu-id="28323-436">String</span></span>|  
|<span data-ttu-id="28323-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-437">COLUMN_GUID</span></span>|<span data-ttu-id="28323-438">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-438">Guid</span></span>|  
|<span data-ttu-id="28323-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-439">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-440">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-440">Int64</span></span>|  
|<span data-ttu-id="28323-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="28323-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="28323-442">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-442">Int64</span></span>|  
|<span data-ttu-id="28323-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-444">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-444">Int64</span></span>|  
|<span data-ttu-id="28323-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="28323-445">IS_NULLABLE</span></span>|<span data-ttu-id="28323-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-446">Boolean</span></span>|  
|<span data-ttu-id="28323-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-447">DATA_TYPE</span></span>|<span data-ttu-id="28323-448">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-448">Int32</span></span>|  
|<span data-ttu-id="28323-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-449">TYPE_GUID</span></span>|<span data-ttu-id="28323-450">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-450">Guid</span></span>|  
|<span data-ttu-id="28323-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="28323-452">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-452">Int64</span></span>|  
|<span data-ttu-id="28323-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="28323-454">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-454">Int64</span></span>|  
|<span data-ttu-id="28323-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="28323-456">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-456">Int32</span></span>|  
|<span data-ttu-id="28323-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="28323-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="28323-458">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-458">Int16</span></span>|  
|<span data-ttu-id="28323-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-459">DESCRIPTION</span></span>|<span data-ttu-id="28323-460">String</span><span class="sxs-lookup"><span data-stu-id="28323-460">String</span></span>|  
|<span data-ttu-id="28323-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="28323-461">OVERLOAD</span></span>|<span data-ttu-id="28323-462">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="28323-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="28323-463">Views</span></span>  
  
|<span data-ttu-id="28323-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-464">ColumnName</span></span>|<span data-ttu-id="28323-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-466">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-467">String</span><span class="sxs-lookup"><span data-stu-id="28323-467">String</span></span>|  
|<span data-ttu-id="28323-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-469">String</span><span class="sxs-lookup"><span data-stu-id="28323-469">String</span></span>|  
|<span data-ttu-id="28323-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-470">TABLE_NAME</span></span>|<span data-ttu-id="28323-471">String</span><span class="sxs-lookup"><span data-stu-id="28323-471">String</span></span>|  
|<span data-ttu-id="28323-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="28323-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="28323-473">String</span><span class="sxs-lookup"><span data-stu-id="28323-473">String</span></span>|  
|<span data-ttu-id="28323-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="28323-474">CHECK_OPTION</span></span>|<span data-ttu-id="28323-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-475">Boolean</span></span>|  
|<span data-ttu-id="28323-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="28323-476">IS_UPDATABLE</span></span>|<span data-ttu-id="28323-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-477">Boolean</span></span>|  
|<span data-ttu-id="28323-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-478">DESCRIPTION</span></span>|<span data-ttu-id="28323-479">String</span><span class="sxs-lookup"><span data-stu-id="28323-479">String</span></span>|  
|<span data-ttu-id="28323-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-480">DATE_CREATED</span></span>|<span data-ttu-id="28323-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-481">DateTime</span></span>|  
|<span data-ttu-id="28323-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-482">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="28323-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-484">Indexes</span></span>  
  
|<span data-ttu-id="28323-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-485">ColumnName</span></span>|<span data-ttu-id="28323-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-487">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-488">String</span><span class="sxs-lookup"><span data-stu-id="28323-488">String</span></span>|  
|<span data-ttu-id="28323-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-490">String</span><span class="sxs-lookup"><span data-stu-id="28323-490">String</span></span>|  
|<span data-ttu-id="28323-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-491">TABLE_NAME</span></span>|<span data-ttu-id="28323-492">String</span><span class="sxs-lookup"><span data-stu-id="28323-492">String</span></span>|  
|<span data-ttu-id="28323-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-493">INDEX_CATALOG</span></span>|<span data-ttu-id="28323-494">String</span><span class="sxs-lookup"><span data-stu-id="28323-494">String</span></span>|  
|<span data-ttu-id="28323-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="28323-496">String</span><span class="sxs-lookup"><span data-stu-id="28323-496">String</span></span>|  
|<span data-ttu-id="28323-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-497">INDEX_NAME</span></span>|<span data-ttu-id="28323-498">String</span><span class="sxs-lookup"><span data-stu-id="28323-498">String</span></span>|  
|<span data-ttu-id="28323-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="28323-499">PRIMARY_KEY</span></span>|<span data-ttu-id="28323-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-500">Boolean</span></span>|  
|<span data-ttu-id="28323-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="28323-501">UNIQUE</span></span>|<span data-ttu-id="28323-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-502">Boolean</span></span>|  
|<span data-ttu-id="28323-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="28323-503">CLUSTERED</span></span>|<span data-ttu-id="28323-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-504">Boolean</span></span>|  
|<span data-ttu-id="28323-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-505">TYPE</span></span>|<span data-ttu-id="28323-506">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-506">Int32</span></span>|  
|<span data-ttu-id="28323-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="28323-507">FILL_FACTOR</span></span>|<span data-ttu-id="28323-508">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-508">Int32</span></span>|  
|<span data-ttu-id="28323-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="28323-509">INITIAL_SIZE</span></span>|<span data-ttu-id="28323-510">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-510">Int32</span></span>|  
|<span data-ttu-id="28323-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="28323-511">NULLS</span></span>|<span data-ttu-id="28323-512">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-512">Int32</span></span>|  
|<span data-ttu-id="28323-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="28323-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="28323-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-514">Boolean</span></span>|  
|<span data-ttu-id="28323-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="28323-515">AUTO_UPDATE</span></span>|<span data-ttu-id="28323-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-516">Boolean</span></span>|  
|<span data-ttu-id="28323-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-517">NULL_COLLATION</span></span>|<span data-ttu-id="28323-518">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-518">Int32</span></span>|  
|<span data-ttu-id="28323-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-520">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-520">Int64</span></span>|  
|<span data-ttu-id="28323-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-521">COLUMN_NAME</span></span>|<span data-ttu-id="28323-522">String</span><span class="sxs-lookup"><span data-stu-id="28323-522">String</span></span>|  
|<span data-ttu-id="28323-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-523">COLUMN_GUID</span></span>|<span data-ttu-id="28323-524">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-524">Guid</span></span>|  
|<span data-ttu-id="28323-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-525">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-526">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-526">Int64</span></span>|  
|<span data-ttu-id="28323-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-527">COLLATION</span></span>|<span data-ttu-id="28323-528">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-528">Int16</span></span>|  
|<span data-ttu-id="28323-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="28323-529">CARDINALITY</span></span>|<span data-ttu-id="28323-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="28323-530">Decimal</span></span>|  
|<span data-ttu-id="28323-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="28323-531">PAGES</span></span>|<span data-ttu-id="28323-532">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-532">Int32</span></span>|  
|<span data-ttu-id="28323-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="28323-533">FILTER_CONDITION</span></span>|<span data-ttu-id="28323-534">String</span><span class="sxs-lookup"><span data-stu-id="28323-534">String</span></span>|  
|<span data-ttu-id="28323-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="28323-535">INTEGRATED</span></span>|<span data-ttu-id="28323-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="28323-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="28323-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="28323-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="28323-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="28323-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-539">Tables</span></span>  
  
-   <span data-ttu-id="28323-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-540">Columns</span></span>  
  
-   <span data-ttu-id="28323-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-541">Procedures</span></span>  
  
-   <span data-ttu-id="28323-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="28323-542">Views</span></span>  
  
-   <span data-ttu-id="28323-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="28323-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="28323-544">Tables</span></span>  
  
|<span data-ttu-id="28323-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-545">ColumnName</span></span>|<span data-ttu-id="28323-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-547">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-548">String</span><span class="sxs-lookup"><span data-stu-id="28323-548">String</span></span>|  
|<span data-ttu-id="28323-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-550">String</span><span class="sxs-lookup"><span data-stu-id="28323-550">String</span></span>|  
|<span data-ttu-id="28323-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-551">TABLE_NAME</span></span>|<span data-ttu-id="28323-552">String</span><span class="sxs-lookup"><span data-stu-id="28323-552">String</span></span>|  
|<span data-ttu-id="28323-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-553">TABLE_TYPE</span></span>|<span data-ttu-id="28323-554">String</span><span class="sxs-lookup"><span data-stu-id="28323-554">String</span></span>|  
|<span data-ttu-id="28323-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-555">TABLE_GUID</span></span>|<span data-ttu-id="28323-556">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-556">Guid</span></span>|  
|<span data-ttu-id="28323-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-557">DESCRIPTION</span></span>|<span data-ttu-id="28323-558">String</span><span class="sxs-lookup"><span data-stu-id="28323-558">String</span></span>|  
|<span data-ttu-id="28323-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-559">TABLE_PROPID</span></span>|<span data-ttu-id="28323-560">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-560">Int64</span></span>|  
|<span data-ttu-id="28323-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-561">DATE_CREATED</span></span>|<span data-ttu-id="28323-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-562">DateTime</span></span>|  
|<span data-ttu-id="28323-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-563">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="28323-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="28323-565">Columns</span></span>  
  
|<span data-ttu-id="28323-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-566">ColumnName</span></span>|<span data-ttu-id="28323-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-568">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-569">String</span><span class="sxs-lookup"><span data-stu-id="28323-569">String</span></span>|  
|<span data-ttu-id="28323-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-571">String</span><span class="sxs-lookup"><span data-stu-id="28323-571">String</span></span>|  
|<span data-ttu-id="28323-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-572">TABLE_NAME</span></span>|<span data-ttu-id="28323-573">String</span><span class="sxs-lookup"><span data-stu-id="28323-573">String</span></span>|  
|<span data-ttu-id="28323-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-574">COLUMN_NAME</span></span>|<span data-ttu-id="28323-575">String</span><span class="sxs-lookup"><span data-stu-id="28323-575">String</span></span>|  
|<span data-ttu-id="28323-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-576">COLUMN_GUID</span></span>|<span data-ttu-id="28323-577">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-577">Guid</span></span>|  
|<span data-ttu-id="28323-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-578">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-579">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-579">Int64</span></span>|  
|<span data-ttu-id="28323-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-581">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-581">Int64</span></span>|  
|<span data-ttu-id="28323-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="28323-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-583">Boolean</span></span>|  
|<span data-ttu-id="28323-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="28323-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="28323-585">String</span><span class="sxs-lookup"><span data-stu-id="28323-585">String</span></span>|  
|<span data-ttu-id="28323-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="28323-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="28323-587">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-587">Int64</span></span>|  
|<span data-ttu-id="28323-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="28323-588">IS_NULLABLE</span></span>|<span data-ttu-id="28323-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-589">Boolean</span></span>|  
|<span data-ttu-id="28323-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-590">DATA_TYPE</span></span>|<span data-ttu-id="28323-591">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-591">Int32</span></span>|  
|<span data-ttu-id="28323-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-592">TYPE_GUID</span></span>|<span data-ttu-id="28323-593">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-593">Guid</span></span>|  
|<span data-ttu-id="28323-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="28323-595">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-595">Int64</span></span>|  
|<span data-ttu-id="28323-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="28323-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="28323-597">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-597">Int64</span></span>|  
|<span data-ttu-id="28323-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="28323-599">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-599">Int32</span></span>|  
|<span data-ttu-id="28323-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="28323-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="28323-601">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-601">Int16</span></span>|  
|<span data-ttu-id="28323-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="28323-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="28323-603">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-603">Int64</span></span>|  
|<span data-ttu-id="28323-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="28323-605">String</span><span class="sxs-lookup"><span data-stu-id="28323-605">String</span></span>|  
|<span data-ttu-id="28323-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="28323-607">String</span><span class="sxs-lookup"><span data-stu-id="28323-607">String</span></span>|  
|<span data-ttu-id="28323-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="28323-609">String</span><span class="sxs-lookup"><span data-stu-id="28323-609">String</span></span>|  
|<span data-ttu-id="28323-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="28323-611">String</span><span class="sxs-lookup"><span data-stu-id="28323-611">String</span></span>|  
|<span data-ttu-id="28323-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="28323-613">String</span><span class="sxs-lookup"><span data-stu-id="28323-613">String</span></span>|  
|<span data-ttu-id="28323-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-614">COLLATION_NAME</span></span>|<span data-ttu-id="28323-615">String</span><span class="sxs-lookup"><span data-stu-id="28323-615">String</span></span>|  
|<span data-ttu-id="28323-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="28323-617">String</span><span class="sxs-lookup"><span data-stu-id="28323-617">String</span></span>|  
|<span data-ttu-id="28323-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="28323-619">String</span><span class="sxs-lookup"><span data-stu-id="28323-619">String</span></span>|  
|<span data-ttu-id="28323-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-620">DOMAIN_NAME</span></span>|<span data-ttu-id="28323-621">String</span><span class="sxs-lookup"><span data-stu-id="28323-621">String</span></span>|  
|<span data-ttu-id="28323-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-622">DESCRIPTION</span></span>|<span data-ttu-id="28323-623">String</span><span class="sxs-lookup"><span data-stu-id="28323-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="28323-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="28323-624">Procedures</span></span>  
  
|<span data-ttu-id="28323-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-625">ColumnName</span></span>|<span data-ttu-id="28323-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="28323-628">String</span><span class="sxs-lookup"><span data-stu-id="28323-628">String</span></span>|  
|<span data-ttu-id="28323-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="28323-630">String</span><span class="sxs-lookup"><span data-stu-id="28323-630">String</span></span>|  
|<span data-ttu-id="28323-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="28323-632">String</span><span class="sxs-lookup"><span data-stu-id="28323-632">String</span></span>|  
|<span data-ttu-id="28323-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="28323-634">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-634">Int16</span></span>|  
|<span data-ttu-id="28323-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="28323-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="28323-636">String</span><span class="sxs-lookup"><span data-stu-id="28323-636">String</span></span>|  
|<span data-ttu-id="28323-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-637">DESCRIPTION</span></span>|<span data-ttu-id="28323-638">String</span><span class="sxs-lookup"><span data-stu-id="28323-638">String</span></span>|  
|<span data-ttu-id="28323-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-639">DATE_CREATED</span></span>|<span data-ttu-id="28323-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-640">DateTime</span></span>|  
|<span data-ttu-id="28323-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-641">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="28323-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="28323-643">Views</span></span>  
  
|<span data-ttu-id="28323-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-644">ColumnName</span></span>|<span data-ttu-id="28323-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-646">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-647">String</span><span class="sxs-lookup"><span data-stu-id="28323-647">String</span></span>|  
|<span data-ttu-id="28323-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-649">String</span><span class="sxs-lookup"><span data-stu-id="28323-649">String</span></span>|  
|<span data-ttu-id="28323-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-650">TABLE_NAME</span></span>|<span data-ttu-id="28323-651">String</span><span class="sxs-lookup"><span data-stu-id="28323-651">String</span></span>|  
|<span data-ttu-id="28323-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="28323-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="28323-653">String</span><span class="sxs-lookup"><span data-stu-id="28323-653">String</span></span>|  
|<span data-ttu-id="28323-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="28323-654">CHECK_OPTION</span></span>|<span data-ttu-id="28323-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-655">Boolean</span></span>|  
|<span data-ttu-id="28323-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="28323-656">IS_UPDATABLE</span></span>|<span data-ttu-id="28323-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-657">Boolean</span></span>|  
|<span data-ttu-id="28323-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28323-658">DESCRIPTION</span></span>|<span data-ttu-id="28323-659">String</span><span class="sxs-lookup"><span data-stu-id="28323-659">String</span></span>|  
|<span data-ttu-id="28323-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="28323-660">DATE_CREATED</span></span>|<span data-ttu-id="28323-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-661">DateTime</span></span>|  
|<span data-ttu-id="28323-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="28323-662">DATE_MODIFIED</span></span>|<span data-ttu-id="28323-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="28323-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="28323-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="28323-664">Indexes</span></span>  
  
|<span data-ttu-id="28323-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="28323-665">ColumnName</span></span>|<span data-ttu-id="28323-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28323-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="28323-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-667">TABLE_CATALOG</span></span>|<span data-ttu-id="28323-668">String</span><span class="sxs-lookup"><span data-stu-id="28323-668">String</span></span>|  
|<span data-ttu-id="28323-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="28323-670">String</span><span class="sxs-lookup"><span data-stu-id="28323-670">String</span></span>|  
|<span data-ttu-id="28323-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-671">TABLE_NAME</span></span>|<span data-ttu-id="28323-672">String</span><span class="sxs-lookup"><span data-stu-id="28323-672">String</span></span>|  
|<span data-ttu-id="28323-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="28323-673">INDEX_CATALOG</span></span>|<span data-ttu-id="28323-674">String</span><span class="sxs-lookup"><span data-stu-id="28323-674">String</span></span>|  
|<span data-ttu-id="28323-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="28323-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="28323-676">String</span><span class="sxs-lookup"><span data-stu-id="28323-676">String</span></span>|  
|<span data-ttu-id="28323-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-677">INDEX_NAME</span></span>|<span data-ttu-id="28323-678">String</span><span class="sxs-lookup"><span data-stu-id="28323-678">String</span></span>|  
|<span data-ttu-id="28323-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="28323-679">PRIMARY_KEY</span></span>|<span data-ttu-id="28323-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-680">Boolean</span></span>|  
|<span data-ttu-id="28323-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="28323-681">UNIQUE</span></span>|<span data-ttu-id="28323-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-682">Boolean</span></span>|  
|<span data-ttu-id="28323-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="28323-683">CLUSTERED</span></span>|<span data-ttu-id="28323-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-684">Boolean</span></span>|  
|<span data-ttu-id="28323-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="28323-685">TYPE</span></span>|<span data-ttu-id="28323-686">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-686">Int32</span></span>|  
|<span data-ttu-id="28323-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="28323-687">FILL_FACTOR</span></span>|<span data-ttu-id="28323-688">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-688">Int32</span></span>|  
|<span data-ttu-id="28323-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="28323-689">INITIAL_SIZE</span></span>|<span data-ttu-id="28323-690">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-690">Int32</span></span>|  
|<span data-ttu-id="28323-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="28323-691">NULLS</span></span>|<span data-ttu-id="28323-692">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-692">Int32</span></span>|  
|<span data-ttu-id="28323-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="28323-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="28323-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-694">Boolean</span></span>|  
|<span data-ttu-id="28323-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="28323-695">AUTO_UPDATE</span></span>|<span data-ttu-id="28323-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="28323-696">Boolean</span></span>|  
|<span data-ttu-id="28323-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-697">NULL_COLLATION</span></span>|<span data-ttu-id="28323-698">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-698">Int32</span></span>|  
|<span data-ttu-id="28323-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="28323-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="28323-700">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-700">Int64</span></span>|  
|<span data-ttu-id="28323-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="28323-701">COLUMN_NAME</span></span>|<span data-ttu-id="28323-702">String</span><span class="sxs-lookup"><span data-stu-id="28323-702">String</span></span>|  
|<span data-ttu-id="28323-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="28323-703">COLUMN_GUID</span></span>|<span data-ttu-id="28323-704">Guid</span><span class="sxs-lookup"><span data-stu-id="28323-704">Guid</span></span>|  
|<span data-ttu-id="28323-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="28323-705">COLUMN_PROPID</span></span>|<span data-ttu-id="28323-706">Int64</span><span class="sxs-lookup"><span data-stu-id="28323-706">Int64</span></span>|  
|<span data-ttu-id="28323-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="28323-707">COLLATION</span></span>|<span data-ttu-id="28323-708">Int16</span><span class="sxs-lookup"><span data-stu-id="28323-708">Int16</span></span>|  
|<span data-ttu-id="28323-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="28323-709">CARDINALITY</span></span>|<span data-ttu-id="28323-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="28323-710">Decimal</span></span>|  
|<span data-ttu-id="28323-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="28323-711">PAGES</span></span>|<span data-ttu-id="28323-712">Int32</span><span class="sxs-lookup"><span data-stu-id="28323-712">Int32</span></span>|  
|<span data-ttu-id="28323-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="28323-713">FILTER_CONDITION</span></span>|<span data-ttu-id="28323-714">String</span><span class="sxs-lookup"><span data-stu-id="28323-714">String</span></span>|  
|<span data-ttu-id="28323-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="28323-715">INTEGRATED</span></span>|<span data-ttu-id="28323-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="28323-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28323-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28323-717">See Also</span></span>  
 [<span data-ttu-id="28323-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="28323-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
