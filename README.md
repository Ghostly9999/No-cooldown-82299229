local v0 = string.char
local v1 = string.byte
local v2 = string.sub
local v3 = bit32 or bit
local v4 = v3.bxor
local v5 = table.concat
local v6 = table.insert

local function v7(v10, v11)
    local v12 = {}
    for v14 = 1, #v10 do
        v6(v12, v0(v4(v1(v2(v10, v14, v14 + 1)), v1(v2(v11, 1 + (v14 % #v11), 1 + (v14 % #v11) + 1))) % 256))
    end
    return v5(v12)
end

local decoded_string1 = v7("\227\214\213\22\227\169\209\23\210\198", "\126\177\163\187\69\134\219\167")

local v8 = game:GetService(decoded_string1).PostSimulation

-- Substituímos a função 'wait' para um tempo de espera extremamente curto
local v9
v9 = hookfunction(wait, function(v13)
    return task.wait(0) or v8:Wait()
end)
