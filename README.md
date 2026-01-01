-- Variáveis
local executor = script.Parent.Executor -- O executor fornecido
local toggleButton = executor.ToggleButton
local duplicadorFrame = executor.DuplicadorFrame
local nomeInput = duplicadorFrame.NomeInput
local duplicarButton = duplicadorFrame.DuplicarButton

-- Função para abrir/fechar o frame
local function toggleDuplicador()
    duplicadorFrame.Visible = not duplicadorFrame.Visible
end

-- Função para duplicar o objeto
local function duplicarObjeto()
    local nomeObjeto = nomeInput.Text
    local objetoOriginal = game.Workspace:FindFirstChild(nomeObjeto)
    if objetoOriginal then
        objetoOriginal:Clone().Parent = game.Workspace
        print("Objeto duplicado com sucesso!")
    else
        warn("Objeto não encontrado!")
    end
end

-- Eventos
toggleButton.MouseButton1Click:Connect(toggleDuplicador)
duplicarButton.MouseButton1Click:Connect(duplicarObjeto)
