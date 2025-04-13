
-- Script de Giros da Sorte BLUE Lock

-- Configurações
local giros = 50
local premios = {
    {nome = "Treinamento intensivo", chance = 20},
    {nome = "Duelo contra um rival", chance = 15},
    {nome = "Acesso ao campo de treinamento avançado", chance = 10},
    {nome = "Análise de jogo com o técnico", chance = 25},
    {nome = "Seleção para o time nacional", chance = 30}
}

-- Função para realizar um giro
local function realizarGiro()
    local sorteio = math.random(1, 100)
    local premioSorteado = nil
    
    local acumulado = 0
    for _, premio in pairs(premios) do
        acumulado = acumulado + premio.chance
        if sorteio <= acumulado then
            premioSorteado = premio.nome
            break
        end
    end
    
    return premioSorteado
end

-- Realizar giros
for i = 1, giros do
    local premio = realizarGiro()
    print("Giro #" .. i .. ": " .. premio)
end
 
