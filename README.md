import pygame

pygame.init()

# Определяем размеры окна
WINDOW_SIZE = (500, 500)

# Создаем окно
screen = pygame.display.set_mode(WINDOW_SIZE)

# Загружаем картинку курсора
cursor_img = pygame.image.load('cursor.png')

# Задаем начальные координаты курсора
cursor_pos = (0, 0)

# Основной цикл программы
while True:
    # Обработка событий
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            quit()

    # Очистка экрана
    screen.fill((0, 0, 0))

    # Получаем координаты курсора мыши
    cursor_pos = pygame.mouse.get_pos()

    # Проверяем, находится ли курсор мыши внутри окна
    if pygame.mouse.get_focused():
        # Рисуем курсор мыши
        screen.blit(cursor_img, cursor_pos)

    # Обновление экрана
    pygame.display.update()
